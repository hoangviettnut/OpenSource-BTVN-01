# A. ĐĂNG KÝ TÊN MIỀN CÁ NHÂN:
## 1. MUA DOMAIN: LUONGHOANGVIET.IO.VN TẠI MATBAO.NET
## 2. ĐĂNG KÝ CLOUDFLARE VÀ THÊM DOMAIN ĐÃ ĐĂNG KÝ VÀO ĐỂ NHẬN 2 NAMESPACE
Nhận 2 nameservers sau khi đăng kí trên cloudflare và add domain:<br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/f89d7fdb-a044-446f-ac8f-cea76ac52e41" /><br>
## 3. NHẬP 2 DÒNG NAMESPACE VÀO DASHBOARD QUẢN LÝ TÊN MIỀN:
Thêm 2 nameservers vừa nhận vào trang quản lý: <br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/c2da62a6-057b-47f7-b110-4d786fe53093" /> <BR>
## 4. SAU KHI ĐÃ LƯU THAY ĐỔI TRÊN MATBAO.NET, QUAY LẠI CLOUDFLARE ĐỂ XÁC NHẬN ĐÃ CẬP NHẬT NAMESERVER.
Đợi Cloudflare update Nameserver:<br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/7fe37a4b-a2e9-4105-9cb5-e3f32333526e" /><br>
## 5. SAU KHI CHECK XONG, CLOUDFLARE THÔNG BÁO:
Thông báo: Your domain is now protected by Cloudflare. Khi này đã kết nối thành cônng! <br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/1252b9d7-728b-486f-ba2b-5f115e69438c" />
## 6. CẤU HÌNH TUNNEL ĐỂ CÁC PHẦN SAU CÓ THỂ TRUY CẬP TRỰC TIẾP TỪ INTERNET:
Truy cập dash.clouflare.com
### B1: Chọn Zero Trust rồi Add Tunnel:
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/5d51996c-5abd-4622-a98a-2f62c83f1700" /><br>
### B2: Đặt tên cho Tunnel (eg. VietDepTrai)<br>
### B3: Cài đặt và run Connector theo hướng dẫn Config trên Cloudflare<br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/a07049af-c216-412a-9e57-32757de5094e" />
Lấy token và sửa file Docker-compose.yml:
<img width="1494" height="762" alt="image" src="https://github.com/user-attachments/assets/fd7cbfdd-29a5-4955-a21c-9bdce4e8b6ad" />
Dùng lệnh "docker-compose up -d" để pull về.
Sau khi cài đặt, làm theo hướng dẫn xong, CloudFlare sẽ báo trạng thái Connected:
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/4dd0465c-c6fb-4f09-b7c4-c0765cd1fccd" /><br>

### B4: Cài đặt Route Tunnel<br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/b6a134c4-c241-4668-8ede-d9d2c0abe746" /<br>

### B5: Kiểm tra trạng thái Tunnel<br>

Status: healthy
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/684d4ca8-10ce-46af-8544-cde056476f1e" /><br>







