## Intruction

The first stage : Scanning

- Khi 1 may tinh chay 1 dich vu, no se can Port de nhan connection. Port la can thiet de thuc hien nhieu yeu cau mang hoac co san nhieu dich vu

- Vi du : Khi ban tai nhieu trang web cung 1 luc trong tirnh duyet wen, chuong trinh phai co cach nao do de xac dinh tab nao dang tai tren trang web nao ( bang cach thiet lap voi may chu web tu xa bang cac port khac nhau tren may cuc bo)

- Hoac ban muon 1 may chu co the chay nhieu dich vu: chay ca HTTP va HTTPs thi can 1 so cach de huongt luu luong truy cap den dich vu thich hop (**It's port**)

- - Ket noi mang duoc thuc hien giua 2 cong ( 1 cong mo lang nghe tren may chu va 1 cong duoc chon ngau nhien tren may tinh cua ban)
 
  - 1 may tinh co 65535 port
 
  -  HTTP : 80 , HTTPS 443  NETBIOS 139  SMB 445
 
  -  Nmap : thuc hien nhieu kieu quet cong khac nhau (kieu pho bien nhat tng so nay)
 
    + B1: No se lan luot ket noi voi tung cong cua muc tieu (Tuy thuoc vao cach phan hoi cua cong, no co the duoc xac nhan la *mo*, *dong*, hoac *loc* (*thuong do tuong lua*)
 
    + B2" Khi biet cong nao dang mo, chung ta co the xem xet liet ke cac dich vu nao dang chay tren moi cong - theo cach thu cong hoac su dung **nmap**

 (Open : Dang co 1 dich vu thuc hien ket noi ra ben ngoai nhung khong bi giam sat boi firewall

 (Close: May muc tieu van nhan va phan hoi nhung khong oc ung dung nao dang nghe tren cong do. Khi do cong duoc bao la dong van co the cho ta biet host dang song

 (Filter: Da co su ngan chan boi tuong lua, ban se chang nhan duoc bat cu phan hoi gi tu muc tieu ca

 (Unfilter: Khong bi chan, nhung khong the biet duoc cong do dong hay mo

 (Open/Filter: khong biet cong mo hay bi loc. No xay ra doi voi kieu quet ma cong du mo nhung khong phan hoi gi ca nen bieu hien cua no giong nhu bi loc

 (Close/Filter: Trang thai xuat hien khi Nmap khong biet duoc port do dang Closed hay Filtered. No duoc su dung cho quet IPID Idle)
 
 - Ly do phai chon nmap? Khong co cong cu quet cong nao khac co chuc nang tuong duong voi chuc nang cua no, manh me hon nho cong cu tao tap lenh co the duoc su dung de quet cac lo hong

 - ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/3659cade-bbbc-4b6f-bf0e-61ed5a2bc3ab)

### Nmap Switches

-sP: su dung Ping de scan Nmap

- sF: su dung FIN scanNmap

- sX: su dung phuong thuc XMAS Scan Nmap

- sN: su dung phuong thuc NULL Scan Nmap

- SR/I RPC su dung de scan RPC

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/358312ae-74c3-4dcc-8ff9-444bc6f59d19)

- quet dong bo : -sS

- quet UDP : -sU

- Phat hien muc tieu dang chay tren he dieu hanh nao : -O

- Phat hien dich vu dang chay tren muc tieu : -sV

- Đầu ra mặc định do nmap cung cấp thường không cung cấp đủ thông tin cho pentester. Bạn sẽ tăng tính dài dòng bằng cách nào? : -V

- Mức độ chi tiết một là tốt, nhưng mức độ dài dòng hai còn tốt hơn! Bạn sẽ đặt mức độ dài dòng thành hai như thế nào?  -VV

-  Luu kqua nmap o 3 dinh dang chinh : -oA

-  Luu kqua nmap o dang "normal" : -oN

-  Luu ket qua o dang "co the phan loai" (gro) : -oG

-  Kich hoat cai dat : -A

-  dat mau thoi gian o cap 5 : -T5

-  Làm thế nào bạn có thể yêu cầu nmap chỉ quét cổng 80?   -p 80

-  Làm thế nào bạn có thể yêu cầu nmap quét các cổng 1000-1500?   -p 1000-1500

-  Làm thế nào bạn có thể yêu cầu nmap quét tất cả các cổng?   -p-

-  Làm cách nào bạn có thể kích hoạt một tập lệnh từ thư viện tập lệnh nmap (nhiều hơn về điều này sau!)?  --script

-  Làm cách nào bạn có thể kích hoạt tất cả các tập lệnh trong danh mục "vuln"?  --script=vuln

- Nmap duoc chay tu terminal. Co phien ban danh cho Windows and Linux. Co the truy cap Nmap bang cach nhap vao dong lenh terminal, theo sau do la 1 so "cong tac" (doi so lenh yeu cau chuong trinh thuc hien nhung viec khac nhau)

+ When port scanning with Nmap, there are three basic scan types. These are:

- TCP Connect Scans (-sT)

- SYN "Half-open" Scans (-sS)

- UDP Scans (-sU)

+ Additionally there are several less common port scan types, some of which we will also cover (albeit in less detail). These are:

- TCP Null Scans (-sN)

- TCP FIN Scans (-sF)

- TCP Xmas Scans (-sX)

Hầu hết trong số này (ngoại trừ quét UDP) được sử dụng cho các mục đích rất giống nhau, tuy nhiên, cách chúng hoạt động khác nhau giữa mỗi lần quét.Điều này có nghĩa là, mặc dù một trong ba lần quét đầu tiên có thể là lựa chọn của bạn trong hầu hết các trường hợp, nhưng bạn nên nhớ rằng vẫn tồn tại các loại quét khác.

Về mặt quét mạng, chúng ta cũng sẽ xem xét ngắn gọn về quá trình quét ICMP (hoặc "ping").
 
### Tim hieu chi tiet ve -sT

- Tóm tắt ngắn gọn, cái bắt tay ba bước bao gồm ba giai đoạn. Đầu tiên, thiết bị đầu cuối kết nối (trong trường hợp này là máy tấn công của chúng tôi) gửi yêu cầu TCP đến máy chủ đích có đặt cờ SYN. Sau đó, máy chủ xác nhận gói này bằng phản hồi TCP chứa cờ SYN cũng như cờ ACK. Cuối cùng, thiết bị đầu cuối của chúng tôi hoàn tất việc bắt tay bằng cách gửi yêu cầu TCP với bộ cờ ACK.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/bbd7eddb-e3db-445a-9451-7dcf680c94b5)

Đúng như tên gọi, quá trình quét TCP Connect hoạt động bằng cách thực hiện bắt tay ba chiều lần lượt với từng cổng mục tiêu. Nói cách khác, Nmap cố gắng kết nối với từng cổng TCP được chỉ định và xác định xem dịch vụ có được mở hay không bằng phản hồi mà nó nhận được.

"... Nếu kết nối không tồn tại (ĐÃ ĐÓNG), thì thiết lập lại sẽ được gửi để phản hồi bất kỳ phân đoạn đến nào ngoại trừ một thiết lập lại khác. Phân đoạn SYN không khớp với kết nối hiện có sẽ bị từ chối theo cách này."

Nói cách khác, nếu Nmap gửi yêu cầu TCP với cờ SYN được đặt thành cổng đóng , máy chủ đích sẽ phản hồi bằng gói TCP có cờ RST (Đặt lại). Bằng phản hồi này, Nmap có thể xác định rằng cổng đã bị đóng.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/b46a0098-8863-4e5a-b770-5f34241cf7ac)

Tuy nhiên, nếu yêu cầu được gửi đến một cổng mở , mục tiêu sẽ phản hồi bằng gói TCP có đặt cờ SYN/ACK. Sau đó, Nmap đánh dấu cổng này là đang mở (và hoàn tất quá trình bắt tay bằng cách gửi lại gói TCP có bộ ACK).

- Kha nang thu 3 : Điều gì sẽ xảy ra nếu cổng mở nhưng ẩn sau tường lửa?

Nhiều tường lửa được cấu hình để loại bỏ các gói tin đến một cách đơn giản. Nmap gửi yêu cầu TCP SYN và không nhận được gì. Điều này cho thấy cổng đang được bảo vệ bởi tường lửa và do đó cổng được coi là bị lọc .
Điều đó nói rằng, rất dễ dàng để cấu hình tường lửa để phản hồi với gói RST TCP. Ví dụ: trong IPtables dành cho Linux , một phiên bản đơn giản của lệnh sẽ như sau:

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/e98e2412-7524-4110-a957-dbee2b44fa2b)

### Quet SYN -sS

-sS) được sử dụng để quét phạm vi cổng TCP của một hoặc nhiều mục tiêu; tuy nhiên, hai loại quét hoạt động hơi khác nhau. Quét SYN đôi khi được gọi là quét " Nửa mở" hoặc quét "Tàng hình" .

Khi quá trình quét TCP thực hiện bắt tay ba chiều đầy đủ với mục tiêu, quá trình quét SYN sẽ gửi lại gói RST TCP sau khi nhận được SYN/ACK từ máy chủ (điều này ngăn máy chủ liên tục cố gắng thực hiện yêu cầu). Nói cách khác, trình tự quét một cổng đang mở sẽ như sau:

![Uploading image.png…]()




