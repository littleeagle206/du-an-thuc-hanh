# Giải trình Chiến lược Kiến trúc Dàn trang (Layout Strategy)

**"CSS Grid sinh ra để làm Layout tổng thể (2D), Flexbox sinh ra để làm Component chi tiết (1D)."**

CSS Grid kiểm soát đồng thời cả hai chiều không gian (hàng và cột) từ vùng chứa cha (Parent-first). Nó là lựa chọn duy nhất đúng đắn cho các bố cục bất đối xứng đa chiều như Bento Dashboard, cho phép một ô tùy ý mở rộng (`span`) qua nhiều hàng/cột mà không làm biến dạng các phần tử lân cận hay phụ thuộc vào các thẻ bao bọc giả lập (`div soup`).

Ngược lại, Flexbox hoạt động theo cơ chế một chiều (Content-first). Nó định vị các phần tử dựa trên kích thước thực tế của nội dung dọc theo một trục đơn lẻ. Flexbox lý tưởng cho thanh điều hướng (Navbar) hoặc các widget con bên trong, giúp các nút bấm và nhãn chữ tự động giãn cách (`space-between`), ngắt dòng mềm mại khi đổi ngôn ngữ mà không bị giới hạn cứng nhắc bởi tọa độ cột.
