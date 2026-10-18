# Nhật Ký Tương Tác AI (AI Prompt Log) - CreativeChronicle Refactoring

### Phiên 1: Khám phá cú pháp dàn trang CSS Grid 2D
* **Prompt gửi AI:** "Trong CSS Grid, làm thế nào để tạo một bố cục dạng khảm (Mosaic) gồm 1 ảnh lớn bên trái chiếm 2 hàng liên tiếp và 2 ảnh nhỏ bên phải nằm chồng lên nhau mà không cần gán chiều cao pixel cố định?"
* **Kiến thức thu được:** Sử dụng thuộc tính `grid-row: span 2` trên phần tử ảnh chính kết hợp với `grid-template-columns: 2fr 1fr` và `grid-auto-rows`. Giải pháp này giữ nguyên luồng tài liệu và hỗ trợ co giãn theo tỷ lệ `aspect-ratio`.
* **Áp dụng:** Triển khai vào lớp `.mosaic-gallery` và `.photo-main` trong `magazine.html`.

---

### Phiên 2: Tận dụng Bootstrap Spacing Utilities và Flexbox Utilities
* **Prompt gửi AI:** "Bootstrap 5 cung cấp những lớp tiện ích nào để căn giữa trục dọc và tạo khoảng cách giữa các phần tử thay vì tự viết mã Flexbox trong file CSS?"
* **Kiến thức thu được:** Bootstrap cung cấp các lớp như `d-flex`, `align-items-center`, `justify-content-between`, và các lớp khoảng cách `g-4`, `gap-3`, `mb-4`.
* **Áp dụng:** Ứng dụng hệ thống thẻ `<div class="row g-4">` và `<div class="col-12 col-md-6 col-lg-3">` cho vùng Recommended Articles để tạo lưới 4 cột đáp ứng đa điểm ngắt mà không cần viết thêm CSS tùy chỉnh.
