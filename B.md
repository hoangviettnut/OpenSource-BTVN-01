# B.Cài đặt Ubuntu + Docker
## 1.Sử dụng VirtualBox để tạo máy ảo và cấu hình mạng cho Ubuntu và VirtualBox
Sau khi tạo thành công máy ảo Ubuntu, đăng nhập vào máy ảo:<br>
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/241b9774-ad3c-4e49-8704-6a1c39010e3e" /><br>
### B1: Cấu hình mạng trên VirtualBox (Tại đây dùng Bridge)
<img width="976" height="647" alt="image" src="https://github.com/user-attachments/assets/287a22ff-fd3e-4d56-843e-4f79a628d48b" /><br>
### B2: Chuẩn bị trên Ubuntu Server
Kiểm tra IP máy ảo: "ip a": 
<img width="1282" height="907" alt="image" src="https://github.com/user-attachments/assets/c1cb0aae-0edb-42a6-8d04-10469e8dfcc5" /><br>
Cài đặt và khởi động OpenSSH Server:<br>
"sudo apt update"<br>
"sudo apt install openssh-server -y"<br>
"sudo systemctl enable --now ssh"<br>
Sau khi chạy các lệnh cài đặt, khởi động xong => mở cổng firewall cho phép connect ssh:<br>
<img width="1282" height="907" alt="image" src="https://github.com/user-attachments/assets/2f6767f0-8063-45ea-9597-3c4f88097bf0" />
### B3: Truy cập SSH từ Windows CMD:
Sử dụng lệnh: "ssh admin@172.20.10.4": 
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/edb6ce57-4880-4006-ae56-06b1447b1c72" />
Khi truy connect thành công hệ thống sẽ báo như ảnh trên.
## 2 Tìm hiểu các lệnh trên Ubuntu:
 --- 1. XEM VÀ ĐIỀU HƯỚNG THƯ MỤC ---<br>
ls                  # Liệt kê file/thư mục cơ bản <br>
ls -la              # Xem chi tiết (kể cả file ẩn, dung lượng và quyền)<br>
cd <đường_dẫn>      # Đi tới thư mục (VD: cd /var/www)<br>
cd ..               # Lùi lại 1 thư mục cha<br>
cd ~                # Trở về thư mục Home của user<br>
mkdir <tên_thư_mục> # Tạo thư mục mới<br>

 --- 2. SAO CHÉP & CHỈNH SỬA FILE ---<br>
cp <file_nguồn> <đường_dẫn_đích>       # Sao chép file<br>
cp -r <thư_mục_nguồn> <đường_dẫn_đích> # Sao chép toàn bộ thư mục (cần -r)<br>
sudo nano <tên_file>                   # Mở file để sửa (Lưu: Ctrl+O -> Enter | Thoát: Ctrl+X)<br>

 --- 3. PHÂN QUYỀN FILE/THƯ MỤC ---<br>
sudo chmod 777 <tên_file>  # Cấp toàn quyền (Đọc/Ghi/Chạy) cho TẤT CẢ mọi người<br>
sudo chmod 755 <tên_file>  # Bạn có toàn quyền, người khác Đọc/Chạy<br>
sudo chmod 644 <tên_file>  # Bạn được Đọc/Ghi, người khác chỉ Đọc<br>

 --- 4. KIỂM TRA MẠNG ---<br>
ip -4 addr          # Xem địa chỉ IP (IPv4)<br>
## 3.Cài đặt Docker:
### B1: Cài đặt các gói phụ thuộc
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
### B2: Thêm GPG Key chính thức của Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
### B3: Thêm Repository của Docker vào hệ thống
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
### B4:Cài đặt Docker Engine
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
### B5: Kiểm tra trạng thái
sudo systemctl status docker
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/a4fcabba-645b-458d-a33a-611fca2e8f79" />
## 4. Kiểm tra phiên bản docker vừa cài đặt, kiểm tra phiên bản của docker compose:
Kiểm tra phiên bản docker vừa cài đặt "docker --version":
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/439faa3c-665e-493c-b2e1-ddf5cc902bc2" />
Kiểm tra phiên bản docker compose "docker compose version":
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/231dd6e5-5097-4c25-b8d2-19c243961247" />
## 5. Cấu hình để docker chạy mà không cần tiền tố sudo
### B1: Thêm user vào group docker
sudo usermod -aG docker $USER<br>
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/14dedccc-34b2-4ae6-828c-d2759e7b94ef" />
### B2: Áp dụng quyền mới
newgrp docker
### B3: Kiểm tra thử với lệnh bất kì
Giờ đây khi dùng lệnh sẽ không cần tiền tố sudo:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/31fa209b-df1d-4471-a90c-c0ec8cbab5e7" /><br>
*** Sau khi remove có thể dùng mà không cần tiền tố sudo.
## 6. Tìm hiểu tập lệnh của docker và docker compose<br>
### Với Docker
 --- IMAGES ---<br>
docker pull <image>         # Tải image về máy<br>
docker images               # Xem danh sách image đã tải<br>
docker rmi <image>          # Xóa image<br>

 --- CONTAINERS ---<br>
docker run -d -p 8080:80 <image>  # Tạo & chạy ngầm, map port (VD: nginx)<br>
docker ps                   # Xem các container ĐANG CHẠY<br>
docker ps -a                # Xem TẤT CẢ container (cả đã tắt)<br>
docker stop <container>     # Dừng container<br>
docker start <container>    # Bật lại container đã dừng<br>
docker rm <container>       # Xóa container (phải stop trước)<br>
docker rm -f <container>    # Ép xóa ngay lập tức<br>

 --- DEBUG ---<br>
docker logs <container>              # Xem log của container<br>
docker exec -it <container> bash     # Chui vào bên trong container gõ lệnh (hoặc dùng 'sh')7<br>
### Với Docker Compose<br>
docker compose up -d        # Tự động tải & chạy tất cả dịch vụ ngầm<br>
docker compose down         # Dừng & xóa sạch các dịch vụ, network<br>
docker compose ps           # Xem trạng thái các dịch vụ trong cụm<br>
docker compose logs -f      # Xem log liên tục của tất cả dịch vụ<br>
## 7.Đảm bảo tường lửa trên Ubuntu đã cho phép các cổng 80, 1880, 9630 (Lệnh: sudo ufw allow ...)
### B1: Kiểm tra FireWall
sudo ufw status
Nếu là inactive thì dùng lệnh "sudo ufw enable"
### B2: mở các port 80, 1880, 9630.
sudo ufw allow 80/tcp
sudo ufw allow 1880/tcp
sudo ufw allow 9630/tcp
*** Nếu yêu cầu root thì sử dụng lệnh sudo !!<br>
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/ea733dcb-ebb2-414a-a118-81c5ed1e4212" />
### B3: Kiểm tra port status
"sudo ufw status"
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/391716e4-ee0b-4625-9899-31314cbc7ae8" />


