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