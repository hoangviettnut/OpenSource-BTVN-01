# C. Cấu hình docker compose
## 1.Tạo thư mục: ~/luongviet
Sử dụng "mkdir ~/luongviet" để tạo thư mục.
## 2. Chuyển vào trong thư mục ~/luongviet
Dùng lệnh "cd ~/luongviet"
## 3. Tạo thư mục ./webcuaviet
Dùng lệnh "mkdir ./webcuaviet"
## 4.Tạo file ./webcuaviet/index.html. Với nội dung là thông tin cá nhân (Phần này thực hiện sau khi đã khởi động docker với các Component cần thiết)
Truy cập "cd ./webcuaviet"
Dùng lệnh "nano index.html" để edit và lưu file:
<img width="1494" height="762" alt="image" src="https://github.com/user-attachments/assets/242d638a-7d0a-447b-bb4b-e15809ec527a" />
Truy cập trang luonghoangviet.io.vn để kiểm tra:
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/0260d236-ac0b-4934-a133-63978308a3fc" />
## 5.Tạo file docker-compose.yml để chứa các dịch vụ yêu cầu:
Quay về ~/luongviet
Dùng lệnh "nano docker-compose.yml" để edit rồi lưu file: 
<img width="1494" height="762" alt="image" src="https://github.com/user-attachments/assets/325225ed-50bd-4c7d-9ad7-2ef50cab048e" /><br>
## 6. Edit file ./nginx/nginx.conf thực hiện các yêu cầu:
Quay về ~/luongviet<br>
Dùng lệnh "mkdir ./nginx" tạo directory<br> 
Dùng lệnh "nano nginx.conf" để edit và lưu file:<br>
<img width="1494" height="762" alt="image" src="https://github.com/user-attachments/assets/c16f0b11-793d-4b96-8596-a01220e9cc64" /><br>
Cấu hình nginx xong chuyển sang Cloudflare để thêm subdomain cho nodered<br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/e589e1e1-bc56-4d9d-8cdc-5db3683ce376" /><br>
Tại đây Sub-Domain trỏ về nodered là: nodered.luonghoangviet.io.vn<br>
## 7. Edit file ./nodered/settings.js để nodered bắt buộc đăng nhập
Tại ~/luongviet
Dùng lệnh "mkdir ./nodered" tạo directory
Chạy Docker-compose lần đầu để Node-RED file cấu hình, dùng lệnh "docker compose up -d":
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/987ea5fd-f5e9-4c86-bd37-d90438b701d9" /><br>
Dùng lệnh "Docker ps" xem đã chạy hay chưa:
<img width="1494" height="762" alt="image" src="https://github.com/user-attachments/assets/97b9fb16-1e07-40e0-b25d-0891e4a4a532" /><br>
Trước khi cấu hình setiing.js, dùng lệnh "docker exec -it my_nodered node -e "console.log(require('bcryptjs').hashSync(process.argv[1], 8));" "viet2004": Tạo hash cho password "viet2004" rồi copy đoạn hash để chỉnh sửa trong setting.js:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/01aec452-40b5-46f1-b501-984d0ed3d69e" />
Hash PW:"$2b$08$tRveBG/8ODlp9QDGphtNvuv9GNdHfnOgR6KsMujnjqswVtBBhv/6O".
Dùng lệnh "nano settings.js" để edit và cấu hình file:
Uncomment phần AdminAuth để cấu hình tài khoản login<br>
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/3cacda11-e944-47c1-8c63-67cf80cbb451" />
Quay lại ~/luongviet và dùng lệnh "docker compose restart nodered" Để khởi động lại hệ thống.
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/d5cbca9c-187f-476c-969b-c8f79500da00" />
Truy cập nodered.luonghoangviet.io.vn để kiểm tra:
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/7c8e7aba-4c9e-49ec-847a-746b1483911e" /><br>
Sau khi đăng nhập ta thấy hiện ra cửa sổ đăng nhập, nhập đúng tài khoản, mật khẩu đã cấu hình ở Settings.jg vào là dùng được: <br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/c849ff60-8a74-4e21-8c61-53b76516368a" />




