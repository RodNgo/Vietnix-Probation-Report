# Mục lục

- [Lưu ý khi Reinstall VPS](#lưu-ý-khi-reinstall-vps)
- [aaPanel Lab](/Week1/LabWebPanel/aaPanel/README.md)
- [CyberPanel Lab](/Week1/LabWebPanel/CyberPanel_Lab/README.md)
- [VestaCP Lab](#vestacp-lab)

---

#### Lưu ý: Khi chuyển giữa các WebPanel thì phải reinstall lại VPS vì không thể cài đặt 2 WebPanel trên cùng 1 VPS. Trên thực tế thì có thể làm như vậy tuy nhiên trong quá trình cài đặt có thể xảy ra xung đột giữa các port mà chúng ta không thể kiểm soát được. Nên để tránh tình trạng đó thì việc reinstall giữa các WebPanel là cần thiết.

## **Lưu ý khi Reinstall VPS**

> Sau khi Reinstall VPS, khi ssh vào lại VPS, bạn sẽ nhận được màn hình như sau:

![Lab Web Panel](/Week1/LabWebPanel/reinstall.png)

- Điều này có nghĩa là key cũ của bạn không còn hợp lệ. Để khôi phục key mới, chạy lệnh sau:

```bash
ssh-keygen -f '/home/rodngo2003/.ssh/known_hosts' -R '14.225.254.83'
```
- Sau đó, bạn có thể ssh vào VPS theo mật khẩu đã đặt tại https://portal.vietnix.vn/ và tiến hành cài đặt các web panel như bình thường.


## **Trỏ domain về 14.225.254.83 để truy cập website.**
- Khi chuyển từ Lab Cpanel qua Lab WebPanel, chúng ta cần trỏ domain về địa chỉ 14.225.254.83 để có thể hiển thị trang web trên từng WebPanel.
> Lưu ý: Chỉ cần trỏ 1 lần vì khi chuyển giữa các WebPanel thì phải Reinstall lại VPS tuy nhiên địa chỉ IP của VPS không thay đổi.