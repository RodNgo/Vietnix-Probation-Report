# Reverse Proxy là gì?

**Reverse Proxy** là một máy chủ trung gian đứng giữa máy khách (client) và máy chủ gốc (backend server). Thay vì kết nối trực tiếp đến máy chủ gốc, các yêu cầu từ máy khách sẽ đi qua Reverse Proxy, sau đó Reverse Proxy sẽ chuyển tiếp yêu cầu đến máy chủ gốc và trả lại phản hồi cho máy khách.

### Lợi ích của Reverse Proxy:
1. **Tăng cường bảo mật**:
   - Che giấu địa chỉ IP và thông tin của máy chủ gốc.
   - Giảm nguy cơ bị tấn công trực tiếp.

2. **Cân bằng tải (Load Balancing)**:
   - Phân phối lưu lượng truy cập đến nhiều máy chủ backend để giảm tải.

3. **Tăng hiệu suất**:
   - Reverse Proxy có thể lưu trữ nội dung tĩnh (cache) để giảm thời gian phản hồi.

4. **Chứng chỉ SSL/TLS**:
   - Reverse Proxy có thể quản lý chứng chỉ SSL để mã hóa kết nối, giảm bớt công việc cho máy chủ backend.

---

# Hướng dẫn cài đặt Reverse Proxy trên aaPanel

## 1. **Cài đặt aaPanel**
Trước tiên, bạn cần cài đặt và truy cập vào aaPanel. Nếu bạn chưa có aaPanel, hãy làm theo hướng dẫn cài đặt từ trang chủ aaPanel hoặc thực hiện trên dòng lệnh (Linux).

Tham khảo tại đây: [Cách cài đặt aaPanel trên VPS](/Week1/LabWebPanel/aaPanel/README.md)

---

## 2. **Truy cập aaPanel**
- Truy cập vào giao diện web của aaPanel thông qua địa chỉ IP hoặc tên miền.
- Đăng nhập vào bảng điều khiển aaPanel.

---

## 3. **Cài đặt Reverse Proxy**
Dưới đây là cách cài đặt Reverse Proxy trong aaPanel:


### Bước 3.2: Thêm website làm Reverse Proxy
1. **Thêm một domain mới**:
   - Vào **Websites** → **Add site** → Nhập tên miền bạn muốn sử dụng làm Reverse Proxy. Ở đây, em sẽ sử dụng tên miền chính để demo đơn gian quá trình chuyển hướng của reverse proxy là ngovinhloc.cloud chuyển hướng đến google.com
   - Lưu ý: Bạn có thể sử dụng IP hoặc tên miền đều được.

2. **Chỉnh sửa cấu hình Reverse Proxy**:
   - Nhấn vào nút **Conf** của website vừa thêm.
   - Trong menu, ở thanh công cụ bên phải, tìm tới **Reverse Proxy**, bạn thực hiện:
     - Chọn **Add Reverse Proxy** (ThêmReverseProxy Reverse Proxy).
     - Nhập Proxy Name và Target URL của máy chủ nguồn mà bạn muốn proxy đến (ví dụ: `https://google.com` hoặc IP của server nguồn).
     - Nhấn **Confirm** để hoàn tất thêm Reverse Proxy.

   ![Reverse Proxy](/Week2/ReverseProxy/ReverseProxy.png)

3. **Kiểm tra và chỉnh sửa thủ công (nếu cần)**:
   - Bạn có thể tùy chỉnh tệp cấu hình Reverse Proxy bằng tay:
     - Với Reverse Proxy: Vào **Reverse Proxy** → **Modify**.
     - Thêm block cấu hình như sau:

     ```nginx
     location / {
         proxy_pass http://127.0.0.1:8080; (nếu website có cấu hình backend ở đây)
         proxy_set_header Host $host;
         proxy_set_header X-Real-IP $remote_addr;
         proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
     }
     ```

   - Lưu lại và kiểm tra.

---

## 4. **Kiểm tra hoạt động**
- Truy cập vào domain hoặc IP bạn vừa cấu hình để kiểm tra xem Reverse Proxy đã hoạt động đúng hay chưa.
- khi truy cập ngovinhloc.cloud thì trả về trang chủ của google thì đã hoạt động thành công.

---

## 5. **Tùy chọn bổ sung**
- **SSL (HTTPS)**:
  - Nếu bạn muốn sử dụng HTTPS, bạn có thể cài đặt chứng chỉ SSL miễn phí từ Let's Encrypt trong phần **SSL** của aaPanel.
  - Khi bật SSL, đảm bảo thêm cấu hình chuyển hướng từ HTTP sang HTTPS.

- **Cache**: Cân nhắc bật cache (bộ nhớ đệm) nếu cần cải thiện hiệu suất.

- **Bảo mật**:
  - Bạn có thể sử dụng tường lửa, giới hạn IP truy cập hoặc cấu hình bảo mật khác từ aaPanel.

## Lưu ý
- **SSL (HTTPS)**: Đảm bảo đã cài đặt SSL cho domain (**`ngovinhloc.cloud`**) trước khi cấu hình Reverse Proxy.
- **Google có thể chặn Reverse Proxy**: Nếu gặp lỗi, thử với một trang web khác không hạn chế proxy.


