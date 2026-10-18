# Báo Cáo Phân Tích: Tác Hại của Position Absolute & Sức Mạnh của CSS Grid

Việc lạm dụng `position: absolute` kèm chiều cao cố định cho mục đích dàn trang là một lỗi kiến trúc nghiêm trọng trong thiết kế đáp ứng (Responsive Design). Thuộc tính này tách hoàn toàn phần tử ra khỏi luồng tài liệu thông thường (document flow), khiến khối cha bị sụp đổ chiều cao về 0. Khi kích thước khung nhìn thu nhỏ trên di động, các phần tử absolute không thể tự co giãn theo ngữ cảnh, dẫn đến hiện tượng đè bẹp lên nhau và che lấp hoàn toàn văn bản bên dưới.

CSS Grid giải quyết triệt để vấn đề này nhờ cơ chế kiểm soát không gian hai chiều (2D) độc lập. Thay vì gán pixel cứng nhắc, Grid bảo tồn trọn vẹn luồng tài liệu tự nhiên, cho phép các phần tử con mở rộng qua nhiều hàng (`grid-row: span 2`) một cách linh hoạt. Kết hợp đơn vị phân số (`fr`) và `gap`, Grid tự động tính toán kích thước các ô ảnh khảm mà không gây ra sai số làm tròn hay đè lấn nội dung lân cận.
