# Nhật ký Tương tác AI (AI Prompt Log) - MetricsHub UI Refactoring

### Giai đoạn 1: Thẩm định & Phân tích lỗi kiến trúc (Architecture Audit)
- **Prompt:** "Khi tôi cần một bố cục mà một phần tử con (Child) phải chiếm chính xác 2 hàng và 2 cột (span 2 rows, 2 columns) đan xen với các phần tử nhỏ khác, tôi nên chọn CSS Grid hay Flexbox? Tại sao Flexbox lại chật vật với yêu cầu này?"
- **Kết quả thu được:** AI phân tích bản chất Flexbox là 1D (dàn hàng hoặc cột độc lập). Khi muốn một khối chiếm 2 hàng trong Flexbox, bắt buộc phải lồng các thẻ `.column` sâu, dẫn tới hiện tượng "Div Soup" và phá vỡ luồng tài liệu khi chuyển sang tablet. Do đó, CSS Grid là lựa chọn chuẩn xác cho Bento Dashboard.

### Giai đoạn 2: Tối ưu khoảng cách và dẹp bỏ Margin lộn xộn
- **Prompt:** "Thuộc tính `gap` hiện nay hỗ trợ trên Flexbox và CSS Grid như thế nào? Tại sao sử dụng `gap` tốt hơn việc căn chỉnh bằng `margin` lộn xộn giữa các phần tử con?"
- **Kết quả thu được:** Thuộc tính `gap` áp dụng trực tiếp lên container cha, tự động tính toán khoảng cách giữa các phần tử mà không gây ra lỗi thừa margin ở phần tử đầu/cuối (loại bỏ sự cần thiết của `:first-child` hay `:last-child`), giúp mã nguồn sạch và giảm thiểu dòng lệnh CSS.

### Giai đoạn 3: Tối ưu hóa lưới 12 cột Bootstrap cho Bảng giá
- **Prompt:** "Trong Bootstrap 5, sự khác biệt giữa `col-12 col-md-4` là gì? Tại sao nên tận dụng hệ thống cột của Bootstrap cho Pricing thay vì tự viết Media Query thủ công?"
- **Kết quả thu được:** Lớp `col-12 col-md-4` tuân thủ chiến lược Mobile-First: mặc định chiếm trọn bề ngang (12 cột) trên di động và tự động chia làm 3 cột bằng nhau khi màn hình đạt điểm ngắt Tablet/Desktop ($\ge 768\text{px}$). Sử dụng lớp tiện ích chuẩn hóa của thư viện giúp tiết kiệm thời gian bảo trì và tránh viết lặp code CSS.
