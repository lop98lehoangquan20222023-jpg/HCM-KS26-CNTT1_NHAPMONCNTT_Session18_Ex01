# Phần 1. Phân tích (DNS là gì?)
- Input (Đầu vào): Tên miền Nam gõ (phong-dieu-phoi.grenlog.vn).

- Output (Đầu ra): Địa chỉ IP của máy chủ (ví dụ: 192.0.2.1).

- Tiến trình DNS Lookup:

   Trình duyệt và máy tính tìm trong bộ nhớ tạm (Cache) xem đã nhớ địa chỉ IP của trang này chưa.

   Nếu chưa có, máy tính hỏi nhà mạng (DNS Resolver).

   Nhà mạng đi hỏi lần lượt từ máy chủ gốc (Root Server), máy chủ đuôi .vn (TLD Server), đến máy chủ quản lý tên miền công ty (greenlog.vn).

   Máy chủ công ty trả về địa chỉ IP chính xác để trình duyệt kết nối.
# Phần 2. Triển khai
- Lỗi DNS:Lỗi ở phía Client (Người dùng). Do gõ sai tên miền nên máy tính không tìm thấy địa chỉ.
Lỗi 500 : Lỗi ở phía Máy chủ, bên trong máy chủ bị lỗi code hoặc quá tải.
- Cách kiểm tra nhanh:
- Mở F12 trên trình duyệt -> chọn thẻ Network ->tải lại trang.Nếu không hiện mã trạng thái (Status) hoặc báo lỗi DNS -> Yêu cầu chưa chạm tới server.
# Phần 3. Kiểm thử (Giả định sửa đúng tên miền nhưng dính lỗi 404)
- Vấn đề: Nếu sửa đúng tên miền thành phong-dieu-phoi.greenlog.vn mà nhận mã 404 Not Found, điều đó có nghĩa là máy chủ vẫn đang hoạt động bình thường.
- Nguyên nhân gây ra lỗi 404: Nam đã gõ sai đường dẫn con