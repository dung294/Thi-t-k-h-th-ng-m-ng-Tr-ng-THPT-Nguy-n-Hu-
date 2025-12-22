# Thi-t-k-h-th-ng-m-ng-Tr-ng-THPT-Nguy-n-Hu-
# Network Design & Implementation for Nguyen Hue High School

## 1. Tổng quan dự án (Project Overview)
Dự án thiết kế hệ thống mạng LAN/WLAN cho trường THPT Nguyễn Huệ nhằm cung cấp hạ tầng kết nối ổn định, bảo mật cho hơn 1000 giáo viên và học sinh. Hệ thống tập trung vào việc phân tách lưu lượng và quản lý tập trung.

## 2. Sơ đồ mạng (Topology)
![Topology Diagram](images/topology.png)
*Kiến trúc: Phân cấp 3 lớp (Hierarchical Design: Core - Distribution - Access).*

## 3. Quy hoạch VLAN (VLAN Planning)
| VLAN | Tên (Name) | Mục đích (Purpose) | Dải IP (Subnet) |
|------|------------|--------------------|-----------------|
| 10   | BGH        | Ban giám hiệu      | 192.168.10.0/24 |
| 20   | GiaoVien   | Phòng hội đồng     | 192.168.20.0/24 |
| 30   | HocSinh    | Phòng máy/Wifi     | 192.168.30.0/24 |
| 40   | Camera     | Hệ thống giám sát  | 192.168.40.0/24 |
| 100  | Management | Quản trị thiết bị  | 192.168.100.0/24|

## 4. Các kỹ thuật đã triển khai (Technical Highlights)
* **Định tuyến (Routing):** Triển khai OSPF để đảm bảo hội tụ mạng nhanh.
* **Dự phòng (Redundancy):** Cấu hình EtherChannel (LACP) giữa Core và Distribution Switch để tăng băng thông và dự phòng lỗi link.
* **Bảo mật (Security):** * Access Control List (ACL) chặn học sinh truy cập VLAN BGH.
    * DHCP Snooping ngăn chặn tấn công DHCP giả mạo.
    * Port Security giới hạn địa chỉ MAC trên các cổng Access.
* **Dịch vụ (Services):** Cấu hình DHCP, NAT, và DNS Server trên thiết bị Cisco.

## 5. Hướng dẫn xem Lab
1. Tải phần mềm **Cisco Packet Tracer v8.2** trở lên.
2. Mở file `NguyenHue_HighSchool_Final.pkt`.
3. Kiểm tra kết nối bằng lệnh `Ping` hoặc `Simulation mode`.
