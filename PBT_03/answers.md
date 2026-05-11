Câu A1:

Inline CSS (Nhúng trực tiếp vào thẻ HTML)

Ví dụ: Tiêu đề

Ưu điểm: Tác dụng ngay lập tức, độ ưu tiên cao nhất.

Nhược điểm: HTML lộn xộn, khó bảo trì, không thể tái sử dụng (lặp code).

Khi nào dùng: Chỉ dùng để test hoặc debug nhanh.

Internal CSS (Viết trong thẻ  ở phần )

Ví dụ:   h1 { color: red; }

Ưu điểm: Gom code vào một chỗ, tái sử dụng được nhiều lần trong cùng một trang đó.

Nhược điểm: Không dùng chung được cho các trang HTML khác, làm file HTML dài và nặng hơn.

Khi nào dùng: Khi làm trang web chỉ có 1 trang duy nhất hoặc làm prototype.

External CSS (Nhúng file .css bên ngoài bằng thẻ )

Ví dụ:

Ưu điểm: Code gọn gàng, tách biệt hoàn toàn HTML và CSS. Dùng chung một file CSS cho hàng trăm trang web khác nhau. Tối ưu tốc độ tải trang nhờ cache trình duyệt.

Nhược điểm: Tốn thêm 1 request mạng để tải file CSS.

Khi nào dùng: Tiêu chuẩn bắt buộc cho 100% dự án thực tế (chuẩn production).

Câu hỏi thêm: Cách nào "thắng"?

Kết quả: Inline CSS sẽ thắng.

Giải thích: CSS hoạt động theo nguyên tắc Specificity (Độ đặc hiệu/Độ ưu tiên). Do Inline CSS được gắn trực tiếp vào chính phần tử đó, trình duyệt đánh giá nó có tính "cụ thể" cao nhất (điểm Specificity cao hơn Internal và External). Do đó, nó sẽ ghi đè các quy tắc bên ngoài để áp dụng lên phần tử.

Câu A2:

h1 → Chọn: ShopTLU

.price → Chọn: 25.990.000đ, 45.990.000đ

#app header → Chọn: Toàn bộ khối tiêu đề và menu chứa các chữ "ShopTLU", "Home", "Products", "About"

nav a:first-child → Chọn: Home

.product.featured h2 → Chọn: MacBook Pro

article > p → Chọn: 25.990.000đ, Mô tả sản phẩm..., 45.990.000đ, Mô tả sản phẩm...

a[href="/"] → Chọn: Home

.top-bar.dark h1 → Chọn: ShopTLU

Câu A3:

Th1: 
Chiều rộng hiện thị = 450px
Không gian chiếm trên trang = 470px

Th2:
Chiều rộng hiện thị = 400px
Kích thước content thực tế = 350px
Không gian chiếm trên trang = 420px

Th3:
Khoảng cách giữa box-a và box-b = 40px

Do quy tắc Margin Collapse (Gộp margin) trong CSS. Khi 2 phần tử nằm dọc sát nhau, margin-bottom của khối trên và margin-top của khối dưới sẽ không cộng dồn. Trình duyệt sẽ cho chúng chồng lên nhau và chỉ lấy giá trị lớn hơn làm kết quả cuối cùng (ở đây 40px > 25px nên lấy 40px).

Câu A4: 

p { color: black; }                    /* Rule A */
.price { color: blue; }               /* Rule B */
#main-price { color: red; }           /* Rule C */
p.price { color: green; }             /* Rule D */

1. Tính specificity score (a, b, c) cho mỗi rule
rule A(0,0,1)
rule B(0,1,0)
rule C(1,0,0)
rule D(0,1,1)
2. Element sẽ có màu đỏ vì selector ID có specificity cao nhất
3. có màu cam
4. có màu đen vì !important có có specificity cao nhất trong tất cả selector

Bài B1:

Element Selector: body, header, table, footer

Class Selector: .menu

ID Selector: #ve-toi

Descendant Selector (Chọn con cháu): .menu ul, .menu a

Pseudo-class (Lớp giả): a:hover, tr:nth-child(even), tr:hover

Bai B2:

Phan 1:

Hộp 1 (content-box): chiều rộng thực tế = 350 px (đo từ DevTools)

Hộp 2 (border-box): chiều rộng thực tế = 300 px (đo từ DevTools)

Giải thích sự khác biệt:

Với content-box (Hộp 1): Kích thước width: 300px bạn khai báo chỉ được tính cho phần "lõi" (content). Khi thêm padding (20px mỗi bên) và border (5px mỗi bên), chúng sẽ cộng dồn ra bên ngoài, làm cái hộp phình to ra. Tổng chiều rộng = 300 + 202 + 52 = 350px.

Với border-box (Hộp 2): Kích thước width: 300px là lệnh ép buộc tổng thể (bao gồm cả content, padding và border). Trình duyệt sẽ tự động bóp nhỏ phần lõi content lại (từ 300px xuống còn 250px) để nhường chỗ cho padding và border, đảm bảo tổng chiều rộng cuối cùng của hộp hiển thị trên màn hình không bao giờ vượt quá 300px.

Phan 2: 

Trường hợp 1: KHÔNG DÙNG border-box (Mặc định là content-box)

Cột trái: 250px (width) + 15px*2 (padding) = 280px

Cột giữa: 500px (width) + 20px*2 (padding) = 540px

Cột phải: 250px (width) + 15px*2 (padding) = 280px

Tính toán: Tổng 3 cột = 280 + 540 + 280 = 1100px.

Giải thích: Vì 1100px > 1000px (chiều rộng của container bọc ngoài), nên container không thể chứa nổi. Giao diện bị vỡ layout, cột cuối cùng sẽ bị rớt xuống dòng dưới.

Trường hợp 2: DÙNG box-sizing: border-box;

Tính toán: Tổng 3 cột = 250 + 500 + 250 = đúng 1000px.

Giải thích: border-box ép trình duyệt tự động bóp nhỏ phần lõi (content) của mỗi cột lại để nhường chỗ cho lớp padding. Nhờ vậy, chiều rộng thực tế hiển thị trên màn hình của mỗi cột được giữ nguyên như khai báo ban đầu. Layout 3 cột nằm vừa vặn, hoàn hảo trong container 1000px.