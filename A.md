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
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/5d51996c-5abd-4622-a98a-2f62c83f1700" />
### B2: Đặt tên cho Tunnel (eg. VietDepTrai)
### B3: Cài đặt và run Connector theo hướng dẫn Config trên Cloudflare
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/a07049af-c216-412a-9e57-32757de5094e" />
Lấy token và sửa file Docker-compose.yml:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/8e0c78e2-9b11-4306-b506-728063711753" />
Sau khi cài đặt, làm theo hướng dẫn xong, CloudFlare sẽ báo trạng thái Connected:
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/eef8a7c4-2178-4381-86bd-ca2dc607c907" />
### B4: Cài đặt Route Tunnel
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/31af806e-d27a-413e-b691-1d5abbad6a72" />
### B5: Kiểm tra trạng thái Tunnel:
Status: healthy
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/ca8e11d2-28fb-45c4-94c7-49e7c90c6b53" />








