# Hướng dẫn cài đặt CyberPanel trên VPS

## **1. Yêu cầu hệ điều hành**

CyberPanel hỗ trợ các hệ điều hành sau:
- **CentOS 7.x**, CentOS 8.x
- **Ubuntu 20.04**, Ubuntu 22.04

Yêu cầu tối thiểu:
- **RAM**: 1GB (khuyến nghị 2GB hoặc hơn để chạy ổn định)
- **CPU**: 1 core
- **Dung lượng ổ cứng**: 10GB trở lên
- **Quyền truy cập root** vào VPS.

---

## **2. Cách cài đặt CyberPanel**

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

![Cyber Panel Lab](/Week1/CyberPanel_Lab/images/SSH.png)

### **Bước 2: Cập nhật hệ thống**
Cập nhật các gói trước khi cài đặt:

```bash
apt update && apt upgrade -y
```

### **Bước 3: Chạy script cài đặt CyberPanel**
Tải và chạy script cài đặt chính thức từ CyberPanel:

```bash
wget -O installer.sh https://cyberpanel.net/install.sh
chmod +x installer.sh
./installer.sh
```

### **Bước 4: Làm theo hướng dẫn cài đặt**
Script sẽ hỏi bạn một số câu hỏi trong quá trình cài đặt. Trả lời như sau:
1. **Chọn phiên bản**:
   - Nhập `1` để cài CyberPanel (phiên bản Open Source).
2. **Cài đặt LiteSpeed Web Server**:
   - Nhập `1` để cài đặt **OpenLiteSpeed** (miễn phí).
3. **Cài đặt Remote MySQL**: 
   - Nhập `N` (thường là không cần thiết cho người mới bắt đầu).
4. **Cài đặt Memcached và Redis** (tùy chọn):
   - Nhập `Y` nếu bạn muốn cải thiện hiệu suất với cache.
5. **Cài đặt Watchdog** (giám sát dịch vụ):
   - Nhập `Y`.

Sau khi hoàn tất, ghi lại thông tin **username**, **mật khẩu**, và **port** được hiển thị trên màn hình.

### **Bước 5: Truy cập giao diện CyberPanel**
- Sau khi cài đặt, ở giao diện terminal sẽ xuất hiện đường dẫn tới màn hình đăng nhập vào CyberPanel và thông tin tài khoản **admin** để đăng nhập. Thông tin đó có dạng như sau

![Cyber Panel Lab](/Week1/CyberPanel_Lab/images/admin.png)

Và về sau mỗi khi ssh vào vps thì đường dẫn sẽ luôn hiện cùng trên màn hình khởi động.

- Mở trình duyệt và truy cập vào:
  ```
   https://14.225.254.83:8090
  ```
- Đăng nhập bằng tài khoản **admin** và mật khẩu được cung cấp trong quá trình cài đặt.

---

## **3. Các thao tác cơ bản trên CyberPanel**

### **1. Tạo một Website**
1. Truy cập vào **Websites** > **Create Website**.
2. Điền thông tin:
   - Chọn gói (package) và tên miền.
   - Nhập địa chỉ email quản trị.
   - Nhấn **Create Website**.

![Cyber Panel Lab](/Week1/CyberPanel_Lab/images/createWebsite.png)


### **2. Tạo và quản lý cơ sở dữ liệu**
1. Truy cập **Databases** > **Create Database**.
2. Điền thông tin:
   - Tên cơ sở dữ liệu, tên người dùng, mật khẩu.
   - Nhấn **Create Database**.

### **3. Cài đặt SSL miễn phí**
1. Truy cập **Websites** > **List Websites**.
2. Nhấn **Issue SSL** để cài đặt chứng chỉ SSL miễn phí từ Let’s Encrypt.

### **4. Quản lý file**
1. Truy cập **File Manager** để upload hoặc chỉnh sửa file.
2. Tải file lên thư mục gốc website: `/home/<tên miền>/public_html`.

---

## **4. Lưu ý**
- Luôn cập nhật hệ thống và CyberPanel để đảm bảo bảo mật.
- Dùng **LiteSpeed Cache** để tối ưu tốc độ website.
- Đổi mật khẩu admin trên giao diện nếu cần theo đường dẫn: 
```
Users > Modify Users.
```
hoặc trên Terminal với câu lệnh
```bash
adminPass --password <Password mới>
```

