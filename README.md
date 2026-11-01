# (Bài tập tổng hợp) Ngày Đầu Thực Tập Dev Tại Công Ty Công Nghệ
Phần A – Profile & Bookmark
Rủi ro dùng chung Profile: Xung đột phiên làm việc (Session Collision), nhầm tài khoản Git, rò rỉ dữ liệu công ty.
Mô hình 3 Profile:
Personal: Dùng cho mục đích cá nhân (MXH, GitHub cá nhân).
Company_Work: Dùng cho công việc (GitHub công ty, web nội bộ test.internal-tool.com).
Sandbox / Dev-Test: Dùng để test giao diện, kiểm thử, cài Extension lạ.
Cấu trúc Bookmark:
📁 01_Work_Internal: test.internal-tool.com, [github.com/company-org](https://github.com/company-org)
📁 02_Dev_Tools: developer.mozilla.org, stackoverflow.com
📁 03_Learning_Resources: leetcode.com, w3schools.com
Cho mượn máy: Cho dùng Guest Mode (Chế độ Khách) để tự động xóa sạch dữ liệu sau khi đóng, không ảnh hưởng Profile chính.
Phần B – Chọn Extension
Nhóm chọn: Dev Suite (ví dụ: JSON Formatter).
Lý do chọn: Tự động thụt lùi dòng, highlight màu và thu gọn/mở rộng node JSON.
2 nhóm còn lại không hợp: Productivity Suite (dành cho văn phòng/ghi chú) và Security Suite (dành cho bảo mật/mật khẩu) không hỗ trợ format JSON.
Cấu hình Site Access: Chọn On click (hoặc On specific sites) theo đúng quy tắc tối thiểu quyền hạn để đảm bảo bảo mật.
Phần C – Luồng HTTP Request
4 Giai đoạn HTTP Request Flow:
DNS Lookup (Tìm IP từ tên miền).
TCP/TLS Connection (Bắt tay thiết lập kết nối).
HTTP Request & Response (Gửi yêu cầu & nhận mã HTML).
Parsing & Rendering (Dựng giao diện CSS/JS/Image).
So sánh Status Code:
404 Not Found: Không tìm thấy tài nguyên | Lỗi Client (URL sai) hoặc Routing Server | Debug: Kiểm tra lại URL hoặc file deploy.
500 Internal Server Error: Lỗi Server nội bộ | Lỗi Server (Backend/Database) | Debug: Xem Response trong Network tab và báo Backend check log.
Tab xem Mã trạng thái: Network Tab (vì Elements xem DOM/CSS, Console xem log JS, Application xem Storage/Cookies).
Phần D – Cache & Cookies
Dev sửa CSS nhưng F5 vẫn cũ:
Nguyên nhân: Dữ liệu bị dính Browser Cache.
Khắc phục: Nhấn Ctrl + Shift + R (Hard Reload) hoặc bật DevTools rồi chọn Empty Cache and Hard Reload.
session_id thiếu HttpOnly:
Rủi ro & Tấn công: Bị tấn công XSS (Cross-Site Scripting), kẻ gian có thể dùng JavaScript để lấy trộm cookie và cướp phiên đăng nhập (Session Hijacking).
Chỉ xóa Session, giữ Cache: Vào tab Application -> Cookies -> Chọn domain -> Xóa dòng cookie session_id (không bấm Clear site data).
Phần E – Debug với DevTools
Sửa màu nút Đăng nhập: Click chuột phải vào nút -> Chọn Inspect (Tab Elements) -> Chỉnh lại thuộc tính background-color ở bảng Styles bên dưới.
Quy trình 4 bước Debug API lỗi:
Bước 1 (Locate): Mở tab Network, tìm request API dòng màu đỏ.
Bước 2 (Inspect Headers): Xem Request URL, Method (GET/POST) và Status Code.
Bước 3 (Check Payload/Response): Kiểm tra dữ liệu gửi đi (Payload) và thông báo lỗi nhận về (Response).
Bước 4 (Formulate Solution): Đưa ra hướng sửa cho Frontend (nếu sai Payload) hoặc Backend (nếu lỗi 500).
Cấu hình Tab Network:
Chỉ xem API: Bật bộ lọc Fetch/XHR.
Không lấy Cache: Tích chọn Disable cache.

