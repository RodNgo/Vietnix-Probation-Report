# Firewall trên Windows Server

Firewall là một lớp bảo mật quan trọng trên Windows Server, giúp bảo vệ hệ thống khỏi các mối đe dọa từ mạng. Trong bài viết này, chúng ta sẽ tìm hiểu về cách hoạt động của Firewall trên Windows Server và cách cấu hình nó.

## 1. Giới thiệu về Firewall

Firewall là một hệ thống bảo mật mạng kiểm soát và giám sát lưu lượng mạng vào và ra, dựa trên các quy tắc bảo mật đã được xác định trước. Trên Windows Server, tính năng này được gọi là **Windows Defender Firewall**.

### Lợi ích của Firewall
- Ngăn chặn truy cập trái phép.
- Bảo vệ hệ thống khỏi các tấn công từ bên ngoài.
- Kiểm soát lưu lượng mạng.
- Giảm thiểu rủi ro lây nhiễm mã độc qua mạng.

## 2. Các thành phần chính của Firewall trên Windows Server

### a. Giao diện quản lý Firewall
Windows Server cung cấp nhiều cách để quản lý Firewall:
- **Windows Defender Firewall with Advanced Security (WFAS):** Cung cấp giao diện chi tiết để cấu hình.
- **PowerShell:** Quản lý Firewall thông qua dòng lệnh.
- **Group Policy:** Cấu hình Firewall cho nhiều máy chủ trong môi trường domain.

### b. Quy tắc (Rules)
- **Inbound Rules:** Quy tắc cho phép hoặc chặn lưu lượng mạng vào hệ thống.
- **Outbound Rules:** Quy tắc cho phép hoặc chặn lưu lượng mạng ra khỏi hệ thống.
- **Connection Security Rules:** Định nghĩa cách bảo mật kết nối giữa các thiết bị.

### c. Hồ sơ (Profiles)
- **Domain Profile:** Áp dụng khi máy chủ kết nối với domain.
- **Private Profile:** Áp dụng khi máy chủ kết nối với mạng riêng.
- **Public Profile:** Áp dụng khi máy chủ kết nối với mạng công cộng.
