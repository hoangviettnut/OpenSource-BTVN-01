# G. Triển khai ứng dụng đến End-user
# Phần A,C đã trình bày rõ cấu hình cho từng yêu cầu, đây chỉ là phần làm lại, tóm tắt:
## 1. CẤU HÌNH TUNNEL ĐỂ CÁC PHẦN SAU CÓ THỂ TRUY CẬP TRỰC TIẾP TỪ INTERNET:
Truy cập dash.clouflare.com
### B1: Chọn Zero Trust rồi Add Tunnel:
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/5d51996c-5abd-4622-a98a-2f62c83f1700" /><br>
### B2: Đặt tên cho Tunnel (eg. VietDepTrai)<br>
## 2 Convert lệnh docker run - sang dạng docker compose và sửa file Docker-Compose.yml<br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/a07049af-c216-412a-9e57-32757de5094e" /><br>
Lấy token và sửa file Docker-compose.yml:
<img width="1494" height="762" alt="image" src="https://github.com/user-attachments/assets/fd7cbfdd-29a5-4955-a21c-9bdce4e8b6ad" /><br>

## 3. Dùng lệnh "docker-compose up -d" để pull về.
Sau khi cài đặt, làm theo hướng dẫn xong, CloudFlare sẽ báo trạng thái Connected:<br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/4dd0465c-c6fb-4f09-b7c4-c0765cd1fccd" /><br>

## 4. Chạy lại Docker compose<br>
Dùng lệnh "docker compose up -d --build":
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/102df3bb-2c64-4402-82b5-9d3aa298a342" /><br>

## 5. Public ứng dụng (Yêu cầu đã được làm chi tiết trong các phần trước đó)
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/b6a134c4-c241-4668-8ede-d9d2c0abe746" /><br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/e589e1e1-bc56-4d9d-8cdc-5db3683ce376" /><br>
Các Domain đã được cấu hình:
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/6b477c68-d26e-407c-9c82-6b3c174f6785" />
## 6. Kiểm tra trạng thái Tunnel<br>
Status: healthy
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/01a037a7-71d2-4696-a941-b830807e5486" /><br>
## 7. Kiểm tra url sub-domain đã hoạt động public cho mọi end-user
Sử dụng điện thoại, bật 4g để truy cập:
