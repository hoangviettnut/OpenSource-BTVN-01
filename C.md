# C. Cấu hình docker compose
## 1.Tạo thư mục: ~/luongviet
Sử dụng "mkdir ~/luongviet" để tạo thư mục.
## 2. Chuyển vào trong thư mục ~/luongviet
Dùng lệnh "cd ~/luongviet"
## 3. Tạo thư mục ./webcuaviet
Dùng lệnh "mkdir ./webcuaviet"
## 4.Tạo file ./webcuaviet/index.html. Với nội dung là thông tin cá nhân
Truy cập "cd ./webcuaviet"
Dùng lệnh "nano index.html" để edit và lưu file:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/c3daf78d-bd94-46a6-b4a9-f8db5131d728" />
## 5.Tạo file docker-compose.yml để chứa các dịch vụ yêu cầu:
Quay về ~/luongviet
Dùng lệnh "nano docker-compose.yml" để edit rồi lưu file: 
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/93486d55-c061-4ff3-a7ef-92432e377945" />
## 6. Edit file ./nginx/nginx.conf thực hiện các yêu cầu:
Quay về ~/luongviet
Dùng lệnh "mkdir ./nginx" tạo directory 
Dùng lệnh "nano nginx.conf" để edit và lưu file:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/6b8bad52-db07-49a8-821e-a342ec29c3f2" />
Tại đây Sub-Domain trỏ về nodered là: nodered.luonghoangviet.io.vn
## 7. Edit file ./nodered/settings.js để nodered bắt buộc đăng nhập
Tại ~/luongviet
Dùng lệnh "mkdir ./nodered" tạo directory
Chạy Dockercompose để Node-RED file cấu hình.
Dùng lệnh "nano setting.js" để edit và cấu hình file.
