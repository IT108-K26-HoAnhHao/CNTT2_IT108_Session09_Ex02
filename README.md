# IT108 - Session09 - Bài2: Kiểm tra tài liệu trước khi xuất bản

## 1. Phần 1: Phân tích lỗi cú pháp trong bản thảo

Dưới đây là các lỗi cú pháp và logic chính trong đoạn mã maux của sinh viên khiến giao diện hiển thị (render) bị lỗi và lộn xộn:

* **Lỗi 1: Vi phạm phân cấp tiêu đề (Heading Hierarchy nhảy cóc)**
  * *Hiện tượng:* Sử dụng thẻ `#` (H1) cho "Tiêu đề 1", sau đó dùng ngay thẻ `###` (H3) cho "Giới thiệu dự án" mà bỏ qua thẻ cấp 2 (`##`).
  * *Nguyên nhân:* Việc nhảy cấp độ tiêu đề làm mất tính liên tục trong cấu trúc logic của tài liệu, khiến các công cụ render hiển thị kích thước chữ không đồng bộ và mất thẩm mỹ.
* **Lỗi 2: Sai cú pháp chèn hình ảnh (Image Syntax)**
  * *Hiện tượng:* Đoạn mã viết `[Logo PTIT] (https://ptit.edu.vn/logo.png)`.
  * *Nguyên nhân:* Tồn tại một **khoảng trắng (space)** ngắt quãng giữa ngoặc vuông `[]` và ngoặc tròn `()`. Cú pháp chuẩn của Markdown bắt buộc phải viết liền khối `[Text hiển thị](đường-dẫn)`. Do khoảng trắng này, trình duyệt không nhận diện được thẻ hình ảnh.
* **Lỗi 3: Vi phạm quy tắc cấu trúc H1 độc nhất và định dạng khối**
  * *Hiện tượng:* Thiếu sự phân tách khoảng trắng rõ ràng giữa các khối nội dung, đồng thời không tuân thủ quy tắc mỗi tài liệu chỉ nên duy trì một tiêu đề H1 chính ở đầu trang.

---

## 2. Phần 2: Hoàn thiện mã nguồn Markdown chuẩn

Dưới đây là đoạn mã Markdown đã được chỉnh sửa hoàn thiện để hiển thị chính xác cấu trúc phân cấp từ H1 đến H2, hình ảnh minh họa và văn bản in đậm:

```markdown
# Tiêu đề 1: Báo cáo Dự án

## Giới thiệu dự án
![Logo PTIT](https://ptit.edu.vn/logo.png)

**Đây là đoạn văn bản in đậm được định dạng chuẩn xác.**

## Mục tiêu
- Quản lý sinh viên
- Quản lý môn học 