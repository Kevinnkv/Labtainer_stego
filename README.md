"Huong dan cau hinh Labtainer:"

Vào gd labedit
New lab -> chọn base2 -> đặt tên lab đúng định dạng
Run -> Build Only
Vào thư mục trunk/labs/ tên lab rồi paste file input
Vào thư mục bin -> mở terminal. NHập nano treataslocal -> nhập “cat”-> Lưu file
Quay lại -> Vào thư mục dockerfile -> bổ sung các thư viện cần cài. Ví dụ:
RUN apt-get update && apt-get install -y --no-install-recommends python3 python3-pip
RUN pip3 install pycryptodome pwntools pyinstaller
RUN pip3 install numpy scipy
Vào gd labedit -> chọn result. Cấu hình checkwork
(File thường có *.stdout hoặc *.stdin; Type:Contains; Nhập đúng string)
Run -> Build Only
Vào thư mục trunk/distrib -> chạy lệnh docker login (Nhập đúng thông tin tài khoản docker)
Vào Config -> start.config -> Thêm dòng thứ 2 là tài khoản docker hub. VD: REGISTRY “tên user docker”
Quay lại terminal docker login: nhập ./publish.py -d -l “tên bài lab”
(nếu lỗi: gõ docker images để kiểm tra xem có tên chưa) Thử Đóng các terminal hiện có rồi kiểm tra lại)
Sau đó kiểm tra trên docker hub đã đẩy image lên chưa.
Copy thư mục bài lab ra thư mục home -> mở terminal gõ tar -cvf tên bài lab.tar tên bài lab -> copy rồi tải lên github
Vào github tạo repo rồi chọn uploading file
Quay lại repo -> copy đường dẫn file .tar dán vào hướng dẫn TH là done.
