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

### B4: Cài đặt Route Tunnel<br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/31af806e-d27a-413e-b691-1d5abbad6a72" /><br>
### B5: Kiểm tra trạng thái Tunnel<br>
Status: healthy
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/684d4ca8-10ce-46af-8544-cde056476f1e" /><br>
