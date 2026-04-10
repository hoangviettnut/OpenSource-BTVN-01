# D.Thêm API
## 1. Tạo thư mục myapi
Tại ~/luongviet dùng lệnh "mkdir ./myapi"
## 2. Tạo file app.py
Tại ./myapi dùng lệnh "nano app.py" để edit và save file:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/4fc926cb-20f8-4899-b529-56dcc2d9f7d7" />
## 3. Tạo file requirements.txt
Tại ./myapi api dùng lệnh "nano requirements.txt" để edit và save file:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/3cf1aa87-3618-411f-8dd7-ef6cd0945932" />
## 4. Tạo Dockerfile để khai báo sử dụng Python 3.9 slim:
Tại ./myapi dùng lệnh "nano Dockerfile" để edit và save file:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/9a7742dc-6bce-434f-9e64-8d007a8cc88e" />
## 5. Sửa đổi docker-compose để phù hợp với phần này: 
Quay về ~/luongviet
Dùng lệnh "nano docker-compose.yml" để edit file, thêm services myapi: 
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/edeaf6d0-5ad6-4a77-a71b-00ed3202bdfb" /><br>
## 6. Sửa đổi nginx/nginx.conf để /api trỏ tới service myapp cổng 9630



