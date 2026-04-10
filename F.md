# F. Gỡ lỗi
## 1. Kiểm tra nhanh
Dùng "Docker compose ps":
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/04dc017d-524b-401e-a5e4-afb6362647fe" /><br>
## 2. Thêm health check & giới hạn Resource cho service myAPI
Sửa service myapi trong docker-compose.yml:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/4d5e4fd8-0079-427c-8996-d1d28c64954a" />
Thêm lệnh cho Dockerfile
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/bc1ac1f3-3fce-4f89-8b4a-fbc03e0413c6" />
## 3. Kiểm tra
Dùng "docker compose up -d --build" để rebuild
Sau đó dùng "docker compose stats" để quan sát lượng ram sử dụng bởi mỗi service:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/5fa7e45c-b11d-4550-8fea-d186f5170558" />
