# H. Câu hỏi về bài làm
## 1. Tại sao phải dùng Nginx làm Reverse Proxy mà không trỏ thẳng Tunnel vào Node-RED?
Việc trỏ trực tiếp Cloudflare Tunnel vào dịch vụ Node-RED chỉ cho phép hệ thống phân phối một ứng dụng duy nhất.
Sử dụng Nginx làm Reverse Proxy cung cấp khả năng định tuyến (Routing) linh hoạt.
Nginx đóng vai trò là cổng giao tiếp trung tâm, phân luồng các yêu cầu dựa trên tên miền phụ (Sub-domain) hoặc đường dẫn (Path) đến các container đích tương ứng trong mạng nội bộ (như Web Frontend, Python API, Node-RED).
Đồng thời, kiến trúc này tối ưu hóa việc phân phối nội dung tĩnh và hỗ trợ khả năng mở rộng hệ thống theo mô hình vi dịch vụ (Microservices).
## 2. Sự khác biệt giữa việc Mount file và Mount thư mục trong Docker là gì?
### Mount thư mục (Directory Bind Mount): 
Đồng bộ hóa toàn bộ cấu trúc và nội dung giữa một thư mục trên máy chủ vật lý (Host) và thư mục trong Container.
Cấu hình này phù hợp cho mã nguồn Web hoặc thư mục lưu trữ dữ liệu cần tính bền vững, nơi các tệp tin thường xuyên được tạo hoặc chỉnh sửa.
### Mount tệp tin (File Bind Mount):
Chỉ đồng bộ hóa một tệp tin duy nhất.
Kỹ thuật này được áp dụng để chèn các tệp cấu hình tùy chỉnh (ví dụ: nginx.conf) vào container mà không ghi đè, làm thay đổi hoặc xóa bỏ các tệp tin hệ thống mặc định khác nằm cùng thư mục đích.
## 3. Nếu thay đổi file index.html ở máy Ubuntu, nội dung trên web có thay đổi ngay không? Tại sao?
Khi nội dung tệp index.html được chỉnh sửa trên máy chủ Ubuntu, giao diện trang web sẽ cập nhật ngay lập tức mà không yêu cầu khởi động lại container.
Nguyên nhân là do cơ chế Bind Mount tạo ra một liên kết tham chiếu trực tiếp ở mức hệ thống tệp (Filesystem level).
Container đọc dữ liệu trực tiếp từ phân vùng ổ cứng của máy chủ Host, do đó mọi thao tác I/O (Đọc/Ghi) được phản ánh theo thời gian thực.
## 4. Docker-compose.yml khai báo các services có phần restart: always hoặc restart: unless-stopped : chúng để làm gì?
Các tham số này nhằm đảm bảo tính sẵn sàng cao (High Availability) cho hệ thống, hỗ trợ khả năng tự phục hồi:
### restart: always: 
Trình nền Docker (Docker Daemon) sẽ liên tục cố gắng khởi động lại container khi có lỗi tiến trình phát sinh hoặc khi máy chủ Host khởi động lại, bất kể trạng thái trước đó của container.
### restart: unless-stopped:
Hoạt động tương tự always, với một ngoại lệ quản trị.
Nếu quản trị viên đã chủ động dừng container bằng lệnh thủ công (docker stop), hệ thống sẽ ghi nhận và không tự động khởi chạy lại container đó trong lần khởi động máy chủ tiếp theo.
## 5. Cách khai báo để tất cả các services đều dùng chung 1 network? Lợi ích của việc khai báo này là gì? Sửa đổi file docker-compose để tất cả các service đều dùng chung 1 network.
Việc đưa tất cả các service vào chung một Network mang lại lợi ích về cơ chế phân giải tên miền nội bộ (Internal DNS Resolution).
Các container có thể giao tiếp trực tiếp với nhau thông qua tên định danh của service thay vì địa chỉ IP vật lý (vốn có đặc tính cấp phát động và dễ thay đổi).
Đồng thời, cấu hình này tạo ra một phân vùng mạng cô lập, tăng tính bảo mật nội bộ.
Cách khai báo trong docker-compose.yml: Thêm khối networks ở cấp cao nhất của tệp, định nghĩa tên mạng với driver là bridge, sau đó gán tham chiếu mạng này vào bên trong từng service.
## 6.Tìm cách đưa Cloudflare Token vào trong file .env rồi sau đó thêm .env vào file .gitignore trước khi push code lên github. Tại sao nói đây là điều quan trọng về bảo mật mã nguồn?
Token của Cloudflare Tunnel là thông tin định danh nhạy cảm cấp quyền truy cập vào hạ tầng mạng.
Nếu khai báo trực tiếp (Hardcode Credentials) vào tệp docker-compose.yml và đồng bộ lên các kho lưu trữ mã nguồn quản lý phiên bản (như GitHub), thông tin này sẽ bị rò rỉ, dẫn đến nguy cơ bị chiếm quyền điều khiển truy cập.
Việc trích xuất Token vào tệp .env và thiết lập quy tắc bỏ qua tệp này trong .gitignore là tiêu chuẩn bảo mật hệ thống (Secret Management), đảm bảo mã nguồn chia sẻ được tách bạch hoàn toàn với dữ liệu xác thực của máy chủ.
## 7. Tại sao chúng ta nên thêm hậu tố :ro khi mount file cấu hình Nginx?
Hậu tố :ro thiết lập đặc quyền chỉ đọc đối với vùng dữ liệu được mount vào container. Đây là một lớp bảo vệ an toàn thông tin thiết yếu.
Trong kịch bản container bị tin tặc khai thác và chiếm quyền điều khiển, đặc quyền :ro ngăn chặn các tiến trình độc hại chỉnh sửa, chèn mã hoặc thay đổi cấu hình gốc (như tệp nginx.conf) trên hệ thống tệp của máy chủ Host vật lý.
## 8. Khi dùng Cloudflare Tunnel: có cần thiết phải mở cổng cho các service nữa không?
Khi luồng mạng được định tuyến qua Cloudflare Tunnel, việc ánh xạ cổng ra bề mặt máy chủ Host (Inbound Port Mapping thông qua khai báo ports) là hoàn toàn không cần thiết và vi phạm nguyên tắc đặc quyền tối thiểu.
Cloudflare Tunnel thiết lập đường hầm dựa trên các kết nối hướng ra ngoài (Outbound Connections) tới các Edge Node của Cloudflare.
Yêu cầu từ máy khách sẽ đi qua Tunnel và phân phối trực tiếp vào mạng nội bộ của Docker.
Kiến trúc mạng Zero Trust này giúp máy chủ Host ẩn danh hoàn toàn khỏi Internet, miễn nhiễm với các kỹ thuật rà quét cổng (Port Scanning) hoặc tấn công DDoS lớp mạng.
