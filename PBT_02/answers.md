Câu A1:

type="email" → Ô nhập text, tự kiểm tra định dạng có ký tự @ → Dùng cho form đăng nhập, đăng ký tài khoản hoặc đăng ký nhận bản tin khuyến mãi.

type="text" → Ô nhập văn bản thông thường, hỗ trợ kiểm tra bằng minlength, maxlength, pattern → Dùng để nhập tên khách hàng, địa chỉ giao hàng hoặc mã giảm giá.

type="password" → Ô nhập ẩn ký tự (dấu chấm hoặc sao), hỗ trợ kiểm tra minlength, pattern → Dùng cho ô nhập mật khẩu khi tạo tài khoản hoặc thanh toán bảo mật.

type="number" → Ô nhập số kèm nút mũi tên tăng/giảm, tự động giới hạn theo min, max, step → Dùng để khách hàng điều chỉnh số lượng sản phẩm trực tiếp trong giỏ hàng.

type="tel" → Hiển thị bàn phím số trên thiết bị di động, hỗ trợ kiểm tra định dạng qua pattern → Dùng cho ô nhập số điện thoại liên hệ ở bước điền thông tin thanh toán (Checkout).

type="date" → Hiển thị bộ chọn ngày (Date picker), tự động giới hạn ngày theo min, max → Dùng để khách hàng chọn ngày mong muốn nhận hàng hoặc nhập ngày tháng năm sinh để nhận mã giảm giá sinh nhật.

type="range" → Hiển thị thanh trượt (Slider), tự động giới hạn giá trị theo min, max, step → Dùng cho bộ lọc khoảng giá tiền (Price range) trong trang danh sách sản phẩm.

type="file" → Nút mở cửa sổ tải tệp tin, tự động lọc định dạng file qua thuộc tính accept và cho phép chọn nhiều file qua multiple → Dùng để khách hàng tải lên hình ảnh thực tế khi viết đánh giá (review) sản phẩm.

type="search" → Ô nhập tìm kiếm có thêm nút "X" để xóa nhanh nội dung → Dùng làm thanh công cụ tìm kiếm sản phẩm chính trên đầu trang web.

type="url" → Ô nhập văn bản tự kiểm tra có đúng định dạng giao thức http:// hoặc https:// → Dùng trong form đăng ký gian hàng của người bán (Seller) để họ cung cấp đường dẫn trang web hoặc mạng xã hội của cửa hàng.

Câu A2:

Trường hợp 1: <!-- User để trống -->

Dự đoán: Trình duyệt sẽ chặn không cho Submit form và hiển thị một thông báo lỗi ngay tại ô input (ví dụ: "Please fill out this field" hoặc "Vui lòng điền vào trường này").

Tại sao: Thuộc tính required quy định đây là trường dữ liệu bắt buộc. Do user để trống (value=""), HTML5 validation sẽ báo lỗi vì không thỏa mãn điều kiện có dữ liệu.

Trường hợp 2: <!-- User gõ "abc" -->

Dự đoán: Form sẽ bị chặn Submit. Trình duyệt hiển thị thông báo lỗi yêu cầu nhập đúng định dạng email (ví dụ: "Please include an '@' in the email address. 'abc' is missing an '@'").

Tại sao: Thẻ input có type="email" mang sẵn cơ chế validation tự động của HTML5 để kiểm tra định dạng email chuẩn (ít nhất phải có ký tự @ và phần tên miền). Chuỗi "abc" không khớp định dạng này nên bị từ chối.

Trường hợp 3: <!-- User gõ 15 -->

Dự đoán: Form bị chặn Submit. Trình duyệt báo lỗi giá trị vượt quá mức cho phép (ví dụ: "Value must be less than or equal to 10").

Tại sao: Thuộc tính max="10" thiết lập giới hạn trên cho ô nhập số (type="number"). Giá trị user nhập là 15, lớn hơn giới hạn tối đa (10) nên không vượt qua được validation.

Trường hợp 4: <!-- User gõ "abc123" -->

Dự đoán: Form bị chặn Submit. Trình duyệt hiện thông báo yêu cầu nhập đúng định dạng được yêu cầu (ví dụ: "Please match the requested format").

Tại sao: Thuộc tính pattern="[0-9]{10}" sử dụng Regular Expression (Biểu thức chính quy) yêu cầu dữ liệu đầu vào phải là đúng 10 chữ số liên tiếp (từ 0 đến 9). Chuỗi "abc123" vừa chứa chữ cái vừa chỉ có 6 ký tự nên vi phạm quy tắc này.

Trường hợp 5: <!-- User gõ "123" -->

Dự đoán: Form bị chặn Submit. Trình duyệt hiển thị cảnh báo chuỗi quá ngắn (ví dụ: "Please lengthen this text to 8 characters or more (you are currently using 3 characters)").

Tại sao: Thuộc tính minlength="8" bắt buộc độ dài tối thiểu của chuỗi nhập vào phải từ 8 ký tự trở lên. Do người dùng chỉ nhập "123" (3 ký tự), validation tự động của HTML5 sẽ bắt lỗi độ dài.

Câu A3:

1. Tại sao <label for="email"> quan trọng cho người dùng screen reader?
Nó liên kết nhãn với thuộc tính id của ô <input>. Nhờ đó, trình đọc màn hình (screen reader) sẽ đọc to tên trường (VD: "Email") thay vì chỉ thông báo chung chung là "ô nhập liệu", giúp người khiếm thị biết chính xác cần điền thông tin gì.

2. Khi nào dùng <fieldset> + <legend>? Cho ví dụ cụ thể.
Dùng để gom nhóm các trường nhập liệu (inputs) có liên quan đến nhau về mặt ngữ nghĩa (như nhóm thông tin địa chỉ, nhóm nút chọn phương thức thanh toán).

HTML
<fieldset>
    <legend>Phương thức thanh toán</legend>
    <input type="radio" id="cod"><label for="cod">Tiền mặt (COD)</label><br>
    <input type="radio" id="bank"><label for="bank">Chuyển khoản</label>
</fieldset>
3. aria-label dùng khi nào? Tại sao KHÔNG nên dùng aria-label khi đã có <label>?

Khi nào dùng: Dùng cho các thành phần tương tác không có chữ hiển thị trên giao diện (VD: nút bấm chỉ có mỗi icon 🛒) để cung cấp nhãn ẩn cho trình đọc màn hình đọc lên.

Tại sao KHÔNG nên dùng chung: Vì trình đọc màn hình sẽ ưu tiên aria-label và ghi đè (bỏ qua hoàn toàn) nội dung của thẻ <label>, gây trùng lặp hoặc xung đột. Nếu thẻ HTML chuẩn (<label>) đã làm tốt nhiệm vụ thì không nên lạm dụng thêm ARIA.

Câu A4:

1. Thuộc tính loading="lazy" trên thẻ <img>

Cải thiện gì: Nó báo cho trình duyệt trì hoãn (delay) việc tải hình ảnh cho đến khi người dùng cuộn chuột đến gần vị trí hình ảnh đó trên màn hình (viewport). Điều này giúp trang web tải nhanh hơn đáng kể ở lần truy cập đầu tiên, tiết kiệm băng thông mạng và tài nguyên hệ thống (đặc biệt hữu ích cho các trang có danh sách sản phẩm dài).

Khi nào KHÔNG nên dùng: KHÔNG nên dùng cho những hình ảnh nằm ở phần hiển thị đầu tiên ngay khi mở web (gọi là vùng above the fold), ví dụ như: logo, ảnh banner chính (hero image), ảnh sản phẩm đầu tiên trên trang chi tiết. Nếu dùng lazy ở đây, người dùng sẽ thấy trang web bị chớp hoặc trống một lúc trước khi ảnh hiện ra, làm giảm trải nghiệm. Những ảnh này nên dùng loading="eager" (mặc định).

2. Tại sao nên cung cấp nhiều <source> trong thẻ <video>?

Tại sao: Trình duyệt web của các hãng khác nhau (Chrome, Safari, Firefox, Edge) không hỗ trợ chung một bộ định dạng (format) hoặc codec video thống nhất. Việc cung cấp nhiều <source> giúp trình duyệt duyệt qua danh sách từ trên xuống dưới và tự động chọn định dạng đầu tiên mà nó có thể đọc được. Điều này đảm bảo video của bạn chạy được trên mọi thiết bị và hệ điều hành.

3 format video web phổ biến:

MP4 (.mp4): Cực kỳ phổ biến, hỗ trợ trên gần như 100% trình duyệt (đặc biệt là Safari/iOS). Thường dùng codec H.264.

WebM (.webm): Do Google phát triển, tối ưu cho web, dung lượng nhẹ, chất lượng cao. Hỗ trợ tốt trên Chrome, Firefox, Edge.

Ogg (.ogv): Định dạng mã nguồn mở, hỗ trợ tốt trên Firefox và Opera cũ, thường dùng làm phương án dự phòng.

3. Thuộc tính alt (Alternative Text) trên <img> dùng để làm gì?

Công dụng: alt cung cấp một đoạn văn bản thay thế để mô tả nội dung bức ảnh. Nó có 3 vai trò chính:

Hiển thị chữ thay thế khi ảnh bị lỗi không tải được (do mạng kém, sai đường dẫn).

Hỗ trợ trình đọc màn hình (Screen Reader) đọc cho người khiếm thị hiểu ảnh vẽ gì (Accessibility).

Giúp các công cụ tìm kiếm (Google SEO) hiểu ngữ cảnh của ảnh để lập chỉ mục.

Viết alt tốt cho 3 trường hợp:

Ảnh sản phẩm iPhone 16: (Mô tả chi tiết để bán hàng)
alt="Điện thoại Apple iPhone 16 Pro Max 256GB màu Titan tự nhiên chụp góc nghiêng"

Ảnh trang trí (decorative - ví dụ đường viền, pattern mờ nền): (Để trống để trình đọc màn hình bỏ qua, không đọc rác)
alt="" (Lưu ý: Bắt buộc phải có thuộc tính alt rỗng, nếu xóa hẳn thuộc tính alt, trình đọc màn hình sẽ đọc nguyên cái tên file).

Ảnh biểu đồ doanh thu Q1/2026: (Nêu bật kết luận/số liệu chính của biểu đồ)
alt="Biểu đồ cột thể hiện doanh thu quý 1 năm 2026 đạt 50 tỷ đồng, tăng 20% so với cùng kỳ năm trước"