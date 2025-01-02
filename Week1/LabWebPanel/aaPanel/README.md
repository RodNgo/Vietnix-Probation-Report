# Hướng dẫn cài đặt aaPanel trên VPS

## **1. Yêu cầu hệ điều hành**

aaPanel hỗ trợ các hệ điều hành sau:
- **CentOS 7.x**, CentOS 8.x
- **Ubuntu 18.04**, Ubuntu 20.04, Ubuntu 22.04
- **Debian 9**, Debian 10, Debian 11

Yêu cầu tối thiểu:
- **RAM**: 512MB (khuyến nghị 1GB hoặc hơn)
- **CPU**: 1 core
- **Dung lượng ổ cứng**: 5GB trở lên
- **Quyền truy cập root** vào VPS.

---

## **2. Cách cài đặt aaPanel**

### **Bước 1: Kết nối vào VPS qua SSH**
Sử dụng công cụ như **PuTTY** (Windows) hoặc **Terminal** (Linux/Mac) để truy cập vào VPS.

Với VPS được anh Đồng Minh Nhật cấp như sau:

```bash
VPS BASIC 3 - vtrainning.16.12.loc

[+] SSH with information:
 * IP: 14.225.254.83
 * Port: 22
 * User: root
 * Password: QHVlG2VGbQaKR9vikpft
```

Cú pháp truy cập vào vps như sau

```bash
ssh root@14.225.254.83
```
Sau đó tiến hành nhập mật khẩu của VPS và truy cập

![aaPanel Lab](/Week1/LabWebPanel/aaPanel/images/SSH.png)

### **Bước 2: Cập nhật hệ thống**
Cập nhật các gói trước khi cài đặt:

```bash
apt update && apt upgrade -y
```

### **Bước 3: Tải và chạy script cài đặt aaPanel**
Sử dụng lệnh sau để tải và cài đặt:

```bash
wget -O install.sh http://www.aapanel.com/script/install_6.0_en.sh
bash install.sh
```

![aaPanel Lab](/Week1/LabWebPanel/aaPanel/images/Install.png)

### **Bước 4: Theo dõi quá trình cài đặt**
- Quá trình cài đặt sẽ mất vài phút.
- Sau khi cài đặt xong, aaPanel sẽ hiển thị thông tin:
  - **URL quản trị** (ví dụ: `http://<IP-VPS>:8888`)
  - **Username**: `admin`
  - **Password**: (mật khẩu được tạo tự động).

Hãy ghi lại thông tin này để sử dụng.

Giao diện **Terminal** sau khi cài đặt xong aaPanel

![aaPanel Lab](/Week1/LabWebPanel/aaPanel/images/InstallSuccess.png)

### **Bước 5: Truy cập giao diện aaPanel**
1. Mở trình duyệt và truy cập vào URL được cung cấp
```
aaPanel Internal Address: https://14.225.254.83:34119/1f713197.

```

2. Đăng nhập bằng **username** và **password** đã cung cấp.

![aaPanel Lab](/Week1/LabWebPanel/aaPanel/images/LoginSite.png)

3. Chọn vào mục **One-click** ở mô hình **LNMP Recommended** và hệ thống sẽ tự động cài đặt các pluggin cài thiết mà không cần phải cài đặt một cách thủ công

![aaPanel Lab](/Week1/LabWebPanel/aaPanel/images/Setup.png)

Đợi một thời gian hệ thống cài đặt xong là có thể sử dụng

![aaPanel Lab](/Week1/LabWebPanel/aaPanel/images/Setup2.png)

### Note: aaPanel có dung lượng cài đặt rất nhẹ nên trong số các WebPanel hiện hành thì aaPanel có thời gian cài đặt có thể nói là nhanh nhất. Do đó, aaPanel được tin tưởng bởi nhiều người dùng cho việc quản lí hosting của họ.

---

## **3. Các thao tác cơ bản trên aaPanel**

### **1. Cài đặt Web Server và Database**
Sau khi đăng nhập:
1. Vào **App Store**.
2. Chọn và cài đặt các thành phần cần thiết như:
   - **Nginx** hoặc **Apache** (Web Server).
   - **MySQL** (Database).
   - **PHP** (Phiên bản phù hợp).

### **2. Tạo Website**
1. Vào **Website** > **Add Site**.
2. Điền thông tin:
   - **Domain**: Tên miền hoặc địa chỉ IP.
   - **Root Directory**: Thư mục gốc của website.
   - **PHP Version**: Chọn phiên bản PHP phù hợp.
3. Nhấn **Submit** để tạo website.

### **3. Quản lý file**
1. Truy cập **File** từ menu chính.
2. Upload file hoặc chỉnh sửa file trực tiếp trong thư mục website (thường nằm trong `/www/wwwroot`).

### **4. Cài đặt SSL miễn phí**
1. Vào **SSL** trong mục quản lý website.
2. Chọn **Let’s Encrypt** và nhấn **Apply** để cài đặt SSL miễn phí.

### **5. Tạo và quản lý cơ sở dữ liệu**
1. Vào **Database** > **Add Database**.
2. Điền thông tin:
   - **Database Name**: Tên cơ sở dữ liệu.
   - **Username** và **Password**: Thông tin người dùng.
   - Nhấn **Submit** để tạo.

---

## **4. Lưu ý**
- Sau khi cài đặt, nên đổi mật khẩu admin để đảm bảo bảo mật. Có thể thay đổi mật trên Terminal bằng câu lệnh:
```
bt 5
```
- Cập nhật các thành phần thường xuyên để đảm bảo an toàn và hiệu suất.
- Backup dữ liệu định kỳ bằng tính năng **Backup** trên aaPanel.

