# Báo cáo Thực hành Headless Commerce - Bagisto
- **Họ và tên:** Nguyễn Minh Hiếu
- **MSSV:** 23810310407
- I. Cài đặt Hệ thống
- <img width="975" height="470" alt="image" src="https://github.com/user-attachments/assets/f2a74ef6-e8f7-4429-8f16-409d75b523a1" />
II. Khai thác GraphQL API
III. Câu hỏi tự luận
1. **So sánh Payload REST và GraphQL:**
 Khác biệt lớn nhất là khắc phục tình trạng Over-fetching (thừa dữ liệu).Với REST API (lấy tất cả), khi ta gọi endpoint của sản phẩm, hệ thống sẽ trả về toàn bộ cấu trúc dữ liệu khổng lồ (id, name, price, stock, variants, images, SEO tags...) dù ta không dùng đến, làm tăng Payload (dung lượng tải). Ngược lại, với GraphQL, ta có quyền chỉ định chính xác các trường cần thiết (ví dụ chỉ lấy id, name, price). Điều này giúp file JSON trả về nhỏ gọn hơn rất nhiều, tiết kiệm băng thông và tăng tốc độ tải trang đáng kể cho ứng dụng Frontend.
2. **Thay đổi giá bằng Query hay Mutation:**
   Em sẽ sử dụng Mutation. Trong kiến trúc GraphQL, Query chỉ được sử dụng cho các hành động đọc dữ liệu (Read/GET) và không làm thay đổi trạng thái của database. Trong khi đó, Mutation được thiết kế riêng cho các thao tác ghi, sửa, hoặc xóa dữ liệu (Create/Update/Delete). Việc thay đổi giá sản phẩm là hành động cập nhật (Update) dữ liệu trong cơ sở dữ liệu, do đó bắt buộc phải sử dụng cấu trúc Mutation.
## IV. Source code Frontend
File `index.html` đính kèm trong repository này.
