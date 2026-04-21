Câu A1 HTTP \& Browser:

1. 5 bước xảy ra khi gõ https://shopee.vn vào trình duyệt và nhấn Enter:
-b1: DNS Lookup \& bắt đầu hành trình: Trình duyệt phân giải tên miền shopee.vn thành địa chỉ IP. Sau đó, một Request xuất phát từ laptop cá nhân của em, đi qua router WiFi và hệ thống mạng cáp quang để tìm đường đến Server (Data center) của Shopee(Tham khảo mục Cuộc Hành Trình 0.3 Giây Xuyên Đại Dương).

\-b2: Client gửi HTTP Request (Gọi món): Trình duyệt (đóng vai trò là Client) gửi một yêu cầu HTTP (thường là lệnh GET) tới Server của Shopee để xin tải trang web(Tham khảo mục 1.1 \& 1.2).

\-b3: Server xử lý yêu cầu (Nhà bếp nấu ăn): Máy chủ của Shopee tiếp nhận HTTP Request, bắt đầu xử lý logic và tổng hợp dữ liệu (thông tin sản phẩm, banner quảng cáo...) (Tham khảo mục 1.1).

\-b4: Server trả về HTTP Response (Giao món): Máy chủ gửi ngược lại một HTTP Response (với mã thành công 200 OK) mang theo các tệp tài nguyên bao gồm HTML (khung xương), CSS (trang trí) và JavaScript (chức năng) chạy qua mạng Internet về lại laptop của em (Tham khảo mục 1.1 \& 3).

\-b5: Browser Rendering (Trình duyệt hiển thị): Ngay khi nhận được các file tài nguyên, Chrome (hoặc trình duyệt của bạn) tiến hành 4 công đoạn để vẽ ra giao diện trang chủ Shopee (Tham khảo mục 1.3).

Nguồn tham chiếu: 01\_introduction\_html\_universe.md và các phần ghi rõ trong từng bước.



2\. Trong DevTools của Chrome, tab Network cho thấy requests/responses

Nguồn tham chiếu: 01\_introduction\_html\_universe.md và phần 4.3. Developer Tools (F12) — "Kính hiển vi" cho website



Câu A2:-Trang web dưới đây bị Google đánh giá SEO thấp vì dùng <div> cho mọi thứ, nên google bot đọc không biết cái nào là gì.
-4 lỗi semantic: <div class="header"> => <header>
		 <div class="menu"> => <nav>

&#x09;	<div class="main"> => <main>

&#x09;	<div class="footer"> =><footer>



Câu A3: Hình vẽ ở folder screenshots.

&#x09;Vì <div> là Block Element nó chiếm cả dòng và tự xuống dòng, còn <span>, <strong> là Inline Element chỉ chiếm nội dung và nằm cùng dòng.



Câu A4:-Sự khác nhau giữa <thead>, <tbody>, <tfoot>:

+)<thead> (Table Head - Phần đầu bảng): Dùng để nhóm các hàng chứa tiêu đề của các cột (thường đi kèm với thẻ <th>). Giúp xác định rõ ý nghĩa dữ liệu của từng cột bên dưới.

+)<tbody> (Table Body - Phần thân bảng): Dùng để chứa toàn bộ các hàng dữ liệu chính của bảng (chứa các thẻ <tr> và <td>). Một bảng có thể có nhiều <tbody> nếu cần phân nhóm dữ liệu lớn.
+)<tfoot> (Table Foot - Phần chân bảng): Dùng để nhóm các hàng mang tính chất tổng kết, tính tổng hoặc chú thích ở cuối bảng


\-KHÔNG NÊN dùng table để tạo layout trang web vì:
+)Rất khó để làm Responsive (Không thân thiện với Mobile):

Cấu trúc của table rất cứng nhắc và khó bẻ gãy. Nếu dùng nó làm layout trang web, khi xem trên các thiết bị màn hình nhỏ (như điện thoại), giao diện sẽ bị thu nhỏ lại đến mức không đọc được hoặc sinh ra thanh cuộn ngang rất khó chịu. Trong khi đó, các công cụ hiện đại như CSS Flexbox và Grid giúp bố cục tự động sắp xếp lại linh hoạt theo mọi kích thước màn hình.
+)Làm hỏng Accessibility (Khả năng tiếp cận) và SEO:

HTML5 quy định mỗi thẻ sinh ra đều có "ngữ nghĩa" riêng. Thẻ <table> có nghĩa là "đây là dữ liệu dạng bảng". Nếu bạn lấy nó làm bố cục, các phần mềm đọc màn hình (Screen Readers) cho người khiếm thị sẽ đọc lộn xộn các hàng/cột khiến họ không thể hiểu được trang web. Đồng thời, các bot tìm kiếm (như Googlebot) cũng bị rối, làm giảm thứ hạng SEO của website.
+)Code bị phình to (Code bloat) và cực kỳ khó bảo trì:

Để tạo ra một layout phức tạp bằng table, bạn bắt buộc phải lồng ghép vô số các thẻ <table>, <tr>, <td> vào bên trong nhau (nested tables). Điều này làm cho file HTML trở nên dài dòng, rối rắm (spaghetti code), trang web tải chậm hơn và biến việc sửa đổi/nâng cấp giao diện sau này thành một "cơn ác mộng" đối với lập trình viên.



