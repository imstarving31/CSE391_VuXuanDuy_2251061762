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

