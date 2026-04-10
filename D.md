# D.Thêm API
## 1. Tạo thư mục myapi
Tại ~/luongviet dùng lệnh "mkdir ./myapi"
## 2. Tạo file app.py
Tại ./myapi dùng lệnh "nano app.py" để edit và save file:
<img width="1494" height="762" alt="image" src="https://github.com/user-attachments/assets/4312bef1-3930-4a6c-8f80-692714de4df2" />
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
Truy cập nginx sau đó dùng lệnh "nano nginx.conf" để chỉnh sửa cho phù hợp với yêu cầu:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/8a8b1282-363b-4688-877e-23ab85433396" />
Sau khi edit xong docker-compose.yml và nginx.conf, dùng lệnh "docker compose up -d --build" để tải và cài đặt python, flask. Dùng thêm "docker compose restart nginx" phòng trường hợp nginx không tự cập nhật:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/ab2ec8c1-4449-4c38-b675-18fdc8a90969" />
Truy cập: "http://luonghoangviet.io.vn/api/" để kiểm tra:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/eb7723a0-1919-4e79-b18b-f97454ee8895" />





