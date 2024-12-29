# Email Relay

### 1. Email Relay là gì?
**Email Relay** là một phương thức cho phép một máy chủ email trung gian chuyển tiếp email từ máy chủ gửi ban đầu đến máy chủ nhận cuối cùng. Nó thường được sử dụng để:

- Gửi email qua một máy chủ đáng tin cậy.
- Tránh các vấn đề về IP bị chặn hoặc bị liệt vào danh sách đen.
- Giảm tải cho máy chủ email nội bộ.


### 2. Các thành phần chính của Email Relay
- **Máy chủ gửi**: Máy chủ ban đầu gửi email (ví dụ: máy chủ ứng dụng, máy chủ website).
- **Máy chủ Relay**: Máy chủ trung gian tiếp nhận email từ máy chủ gửi và chuyển tiếp đến đích.
- **Máy chủ nhận**: Máy chủ nhận cuối cùng của email (thường là máy chủ của nhà cung cấp dịch vụ email như Gmail, Yahoo Mail, v.v.).



### 3. Lợi ích của Email Relay
- **Bảo mật tốt hơn**: Bảo vệ thông tin và giảm thiểu nguy cơ email bị đánh dấu là spam.
- **Cải thiện độ tin cậy**: Đảm bảo email được gửi từ các máy chủ có uy tín.
- **Giảm tải cho máy chủ nội bộ**: Máy chủ Relay xử lý và quản lý việc gửi email với số lượng lớn.


### 4. Cách hoạt động của Email Relay
1. **Bước 1**: Máy chủ gửi chuyển email đến máy chủ Relay.
2. **Bước 2**: Máy chủ Relay xác thực email (dựa trên các tiêu chí như SPF, DKIM, v.v.).
3. **Bước 3**: Máy chủ Relay chuyển tiếp email đến máy chủ nhận cuối cùng.



### 5. Các giao thức phổ biến trong Email Relay
- **SMTP (Simple Mail Transfer Protocol)**: Là giao thức chuẩn để gửi email.
- **TLS/SSL**: Được sử dụng để mã hóa và bảo mật quá trình chuyển email.



# FTP Account

### 1. FTP là gì?
FTP (File Transfer Protocol) là một giao thức chuẩn dùng để truyền tải tệp tin giữa máy tính cá nhân và máy chủ qua mạng Internet hoặc mạng nội bộ. **FTP Account** là tài khoản được tạo ra để truy cập và quản lý tệp trên máy chủ thông qua FTP.



### 2. Các thành phần chính của FTP Account
1. **Tên tài khoản (Username)**: Dùng để định danh tài khoản FTP.
2. **Mật khẩu (Password)**: Bảo mật và đảm bảo chỉ người dùng có quyền mới được truy cập.
3. **Địa chỉ máy chủ (Host)**: Địa chỉ IP hoặc tên miền của máy chủ FTP.
4. **Cổng kết nối (Port)**:
   - Mặc định: `21` (FTP) hoặc `22` (SFTP - Secure FTP).
5. **Thư mục gốc (Root Directory)**: Vị trí thư mục mà tài khoản FTP có quyền truy cập.



### 3. Lợi ích của FTP Account
- **Quản lý tệp dễ dàng**: Tải lên và tải xuống tệp từ máy chủ nhanh chóng.
- **Chia sẻ dữ liệu**: Cho phép nhiều người dùng truy cập các thư mục nhất định.
- **Bảo mật**: Hỗ trợ mã hóa kết nối thông qua FTPS hoặc SFTP.
- **Hỗ trợ đa nền tảng**: FTP có thể hoạt động trên nhiều hệ điều hành khác nhau.

