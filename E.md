# E. Triển khai ứng dụng
## 1. Chuyển vào trong thư mục ~/luongviet
Dùng lệnh "cd ~/luongviet"
## 2. Gõ lệnh để docker compose chạy
Dùng lệnh "docker compose up -d":
<img width="1494" height="762" alt="image" src="https://github.com/user-attachments/assets/ffb0c429-4086-416a-b77d-26e96365222e" /><br>
## 3. Kiểm tra các container đang chạy trong docker
Dùng lệnh "docker ps" hoặc "docker compose ps":
<img width="1494" height="762" alt="image" src="https://github.com/user-attachments/assets/3945980c-8a85-4b2b-91ec-36691955a87c" />
## 4. Kiểm tra kiểm thử các service đang chạy độc lập thông qua ip và port của nó
### B1: Kiểm tra Nodered, truy cập: http://192.168.1.3:1880/ 
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/11ab5dd8-f2b0-4cf9-b423-ea0ae26f16b5" /><br>
### B2: Kiểm tra API, truy cập: http://192.168.1.3:9630/
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/0660a521-3ade-49d3-87e7-a700478d7306" /><br>
### B3: Kiểm tra Nginx, truy cập http://192.168.1.3:80/
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/cea974a1-aa16-41bf-9e53-2ad18c7b04dc" />
## 5. Sử dụng nodered để tạo get API đơn giản: 
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/c1fd7907-1a2b-4073-8085-daa8d003a543" /><br>
Nodered đã được cấu cấu hình trong nginx.conf.<br>
## 6. Sửa file ./myweb/index.html
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/2662232b-0bc3-4f67-a857-a009000487ed" />
Quay về ~/luongviet và dùng lệnh "docker exec my_nginx nginx -s reload" để reload website.
Truy cập để kiểm tra:
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/802476b0-499d-4455-8483-4e0ff3f98751" />






