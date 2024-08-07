>Trên thực tế, chức năng trong trình duyệt sử dụng cùng một giao thức chính xác mà chúng ta sẽ sử dụng ngày hôm nay. Giao thức này được gọi là Secure Hell hoặc viết tắt là SSH và là phương tiện phổ biến để kết nối và tương tác với dòng lệnh của máy Linux từ xa .

- Chúng tôi sẽ triển khai hai máy trong phòng này:

`
Máy Linux của bạn
Hộp tấn công TryHackMe
`

### SSH là gì và nó hoạt động như thế nào?

Secure Shell hay SSH chỉ đơn giản là một giao thức giữa các thiết bị dưới dạng được mã hóa. Sử dụng mật mã, bất kỳ dữ liệu đầu vào nào chúng ta gửi ở định dạng mà con người có thể đọc được đều được mã hóa để truyền qua mạng -- sau đó dữ liệu này sẽ không được mã hóa khi đến máy từ xa, như trong sơ đồ bên dưới

![image](https://github.com/user-attachments/assets/fb9de400-b261-4a3b-861e-7d31726ed6cf)

Bạn có thể tìm hiểu về các loại mã hóa khác nhau trên phòng TryHackMe. Nhưng hiện tại, chúng ta chỉ cần hiểu rằng:

SSH cho phép chúng ta thực hiện lệnh từ xa trên một thiết bị khác.

Bất kỳ dữ liệu nào được gửi giữa các thiết bị đều được mã hóa khi nó được gửi qua mạng như Internet

### Triển khai máy Linux của bạn

Nhấn nút màu xanh lá cây "Khởi động máy" ở góc trên bên phải của tác vụ này, sau đó cuộn lên đầu trang để xem thông tin triển khai như sau:

![image](https://github.com/user-attachments/assets/98dbc240-469f-44bf-abc9-5911cde57aca)

Địa chỉ IP được hiển thị là địa chỉ của máy Linux mà bạn sẽ đăng nhập bằng SSH . Hãy lưu ý điều này ngay bây giờ.

### Triển khai TryHackMe AttackBox

Nhìn vào đầu trang, nhấn nút "Start AttackBox" để triển khai TryHackMe AttackBox mà chúng ta sẽ tương tác. TryHackMe AttackBox là một máy Ubuntu Linux được lưu trữ trực tuyến trên đám mây và có thể tương tác thông qua trình duyệt của bạn. Bạn sẽ sử dụng máy này để tương tác với máy mà bạn triển khai trong tác vụ này.

![image](https://github.com/user-attachments/assets/624ada87-d99b-42bb-b790-0e1ffb9967d3)

### Sử dụng SSH để đăng nhập vào máy Linux của bạn

`
Cú pháp để sử dụng SSH rất đơn giản. Chúng ta chỉ cần cung cấp hai thứ:

1. Địa chỉ IP của máy từ xa

2. Sửa thông tin đăng nhập vào tài khoản hợp lệ để đăng nhập trên máy từ xa
`

Đối với phòng này, chúng ta sẽ đăng nhập với tư cách là "tryhackme", mật khẩu là "tryhackme" không có dấu ngoặc kép (""). Hãy sử dụng địa chỉ IP của máy được hiển thị trong thẻ ở đầu phòng làm địa chỉ IP và người dùng này, để xây dựng lệnh đăng nhập vào máy từ xa bằng SSH . Lệnh để thực hiện là sshvà sau đó là tên người dùng của tài khoản, @địa chỉ IP của máy.

Vi du ssh tryhackme@10.10.187.97 

Thay thế địa chỉ IP bằng địa chỉ IP cho máy đích Linux của bạn. Sau khi thực hiện, chúng tôi sẽ được yêu cầu tin tưởng máy chủ và sau đó cung cấp mật khẩu cho tài khoản " tryhackme ", cũng là " tryhackme ".

![image](https://github.com/user-attachments/assets/5bcb16d7-6641-4e1c-a909-003ee9d7be86)

![image](https://github.com/user-attachments/assets/53139ce9-ace4-429a-af68-65a62c708dfa)

*Lưu ý: Khi bạn nhập mật khẩu vào dấu nhắc đăng nhập ssh, sẽ không có phản hồi nào hiển thị -- bạn sẽ không thể thấy bất kỳ văn bản hoặc ký hiệu nào xuất hiện khi bạn nhập mật khẩu. Tuy nhiên, nó vẫn hoạt động, vì vậy chỉ cần nhập mật khẩu và nhấn enter để đăng nhập.*

## 3. Introduction to Flags and Switches

Phần lớn các lệnh cho phép cung cấp đối số. Các đối số này được xác định bằng dấu gạch nối và một từ khóa nhất định được gọi là cờ hoặc công tắc.

Sau này chúng ta sẽ thảo luận về cách xác định lệnh nào cho phép cung cấp đối số và hiểu chính xác những lệnh này có tác dụng gì.

Khi sử dụng lệnh, trừ khi được chỉ định khác, lệnh sẽ thực hiện hành vi mặc định của nó. Ví dụ,  ls liệt kê nội dung của thư mục làm việc. Tuy nhiên, các tệp ẩn không được hiển thị. Chúng ta có thể sử dụng cờ và công tắc để mở rộng hành vi của lệnh.

Sử dụng lsví dụ của chúng tôi, lsthông báo cho chúng tôi rằng chỉ có một thư mục có tên "folder1" như được tô sáng trong ảnh chụp màn hình bên dưới

![image](https://github.com/user-attachments/assets/f2deebd1-55d8-4cc6-9ea6-77fad0399566)

*Tuy nhiên, sau khi sử dụng -ađối số (viết tắt của --all), chúng ta đột nhiên có kết quả đầu ra với một vài tệp và thư mục khác như ".hiddenfolder". Các tệp và thư mục có " . " là các tệp ẩn.*

![image](https://github.com/user-attachments/assets/920d5ebe-6646-4075-ad0e-a4ebe6a7f900)

Các lệnh chấp nhận những tùy chọn này cũng sẽ có một --helptùy chọn. Tùy chọn này sẽ liệt kê các tùy chọn có thể mà lệnh chấp nhận, cung cấp mô tả ngắn gọn và ví dụ về cách sử dụng.

![image](https://github.com/user-attachments/assets/9b991c7a-cc9e-4885-bb9a-f2f6aadd771a)

### Trang Man(ual)

#### Hướng dẫn https://linux.die.net/man/

Để truy cập tài liệu này, chúng ta có thể sử dụng lệnh man và sau đó cung cấp lệnh mà chúng ta muốn đọc tài liệu. Sử dụng ví dụ ls của chúng ta, chúng ta sẽ sử dụng man lsđể xem các trang hướng dẫn như lssau:

![image](https://github.com/user-attachments/assets/bd12d8dd-f11b-4080-8514-fec1c4fad042)

![image](https://github.com/user-attachments/assets/1965d71b-7335-4381-8af2-c2ed0830b72a)

## 4. Filesystem Interaction Continued

Trong nhiệm vụ này, chúng ta sẽ tìm hiểu thêm một số lệnh để tương tác với hệ thống tập tin nhằm cho phép chúng ta:

- tạo tập tin và thư mục

- di chuyển các tập tin và thư mục

- xóa các tập tin và thư mục

![image](https://github.com/user-attachments/assets/fcb87b5e-0f03-4cdd-b4c4-3640147c2137)

#### Tạo tập tin và thư mục (touch, mkdir)

- Tạo tệp và thư mục trên Linux là một quá trình đơn giản. Trước tiên, chúng ta sẽ tìm hiểu về việc tạo tệp. Lệnh touch chỉ có một đối số -- tên mà chúng ta muốn đặt cho tệp mà chúng ta tạo. Ví dụ, chúng ta có thể tạo tệp "note" bằng cách sử dụng touch note. `Cần lưu ý rằng touch chỉ tạo một tệp trống`. Bạn sẽ cần sử dụng các lệnh như echo hoặc trình soạn thảo văn bản như nano để thêm nội dung vào tệp trống.

![image](https://github.com/user-attachments/assets/a1e025b1-b1df-4247-a97f-eb29c4128d12)

- Đây là một quá trình tương tự để tạo một thư mục, chỉ bao gồm việc sử dụng lệnh mkdirvà một lần nữa cung cấp tên mà chúng ta muốn gán cho thư mục. Ví dụ, tạo thư mục "mydirectory" bằng cách sử dụng mkdir mydirectory.

 ![image](https://github.com/user-attachments/assets/6c243230-c6af-4686-b585-72840548e45f)

#### Xóa Tệp và Thư mục (rm)

rm là lệnh đặc biệt nhất trong số các lệnh mà chúng ta đã đề cập cho đến nay. Bạn có thể dễ dàng xóa các tệp bằng cách sử dụng rm. Tuy nhiên, bạn cần cung cấp -Rcông tắc cùng với tên thư mục bạn muốn xóa.

![image](https://github.com/user-attachments/assets/7c6b46f4-924d-44f8-89c1-f048ba5464ad)

#### Sao chép và di chuyển tập tin và thư mục (cp, mv)

![image](https://github.com/user-attachments/assets/c6f8dbd6-290e-41f7-b207-748dbc370253)

Di chuyển một tệp cần hai đối số, giống như lệnh cp. Tuy nhiên, thay vì sao chép và/hoặc tạo tệp mới, mvsẽ hợp nhất hoặc sửa đổi tệp thứ hai mà chúng tôi cung cấp làm đối số. Bạn không chỉ có thể sử dụng mvđể di chuyển tệp đến thư mục mới mà còn có thể sử dụng mv để đổi tên tệp hoặc thư mục. Ví dụ, trong ảnh chụp màn hình bên dưới, chúng tôi đang đổi tên tệp "note2" thành "note3". "note3" bây giờ sẽ có nội dung của "note2". 

![image](https://github.com/user-attachments/assets/11d014c2-619d-487c-a4bd-6ad8acfd5bb2)

### Xác định loại tệp

Cho đến nay, các tệp chúng ta đã sử dụng trong các ví dụ của mình chưa có phần mở rộng. Nếu không biết bối cảnh tại sao tệp đó lại ở đó -- chúng ta thực sự không biết mục đích của nó. Nhập lệnh file. Lệnh này có một đối số. Ví dụ, chúng ta sẽ sử dụng fileđể xác nhận xem tệp "note" trong các ví dụ của chúng ta có thực sự là tệp văn bản hay không, như sau file note.

![image](https://github.com/user-attachments/assets/fa44e0e6-60b9-4e66-812a-bcb8455c5f8d)

![image](https://github.com/user-attachments/assets/f853a5a0-a9ba-42c2-9d58-1883f73f7ac0)

## 5. Permissions 101

![image](https://github.com/user-attachments/assets/437d8dca-7d65-4738-9897-52cbed3703ab)

Mặc dù đáng sợ, ba cột này rất quan trọng trong việc xác định một số đặc điểm của tệp hoặc thư mục và liệu chúng ta có quyền truy cập vào tệp hoặc thư mục đó hay không. Tệp hoặc thư mục có thể có một số đặc điểm xác định cả hành động nào được phép và người dùng hoặc nhóm nào có khả năng thực hiện hành động đã cho -- chẳng hạn như sau:

**Đọc**

**Viết**

**Thi hành**

#### Tóm tắt: Sự khác biệt giữa Người dùng và Nhóm

Hãy đưa điều này vào bối cảnh thực tế; người dùng hệ thống chạy máy chủ web phải có quyền đọc và ghi tệp cho một ứng dụng web hiệu quả. Tuy nhiên, các công ty như công ty lưu trữ web sẽ phải muốn cho phép khách hàng của họ tải tệp của riêng họ lên trang web của họ mà không phải là người dùng hệ thống máy chủ web -- làm ảnh hưởng đến tính bảo mật của mọi khách hàng khác. 

#### Chuyển đổi giữa người dùng

Việc chuyển đổi giữa những người dùng trên bản cài đặt Linux rất dễ dàng nhờ lệnh su. Trừ khi bạn là người dùng root (hoặc sử dụng quyền root thông qua sudo), thì bạn cần biết hai điều để tạo điều kiện thuận lợi cho việc chuyển đổi tài khoản người dùng này:

- Người dùng chúng tôi muốn chuyển sang

- Mật khẩu của người dùng

Đơn giản, bằng cách cung cấp lệnh -l chuyển đổi tới su, chúng ta sẽ khởi động một shell giống với người dùng thực tế đang đăng nhập vào hệ thống hơn - chúng ta thừa hưởng nhiều thuộc tính hơn của người dùng mới, tức là các biến môi trường, v.v. 

![image](https://github.com/user-attachments/assets/e4dd37fe-3c31-4b9f-b043-1a572ded487b)

Ví dụ, khi sử dụng suđể chuyển sang "user2", phiên mới sẽ đưa chúng ta đến thư mục gốc của người dùng trước đó. 

![image](https://github.com/user-attachments/assets/f623361f-6c12-4a0c-a4e9-fbccf998ae3e)

Bây giờ, sau khi sử dụng -l, phiên làm việc mới của chúng ta đã tự động đưa chúng ta đến thư mục gốc của "người dùng". 

## 6. Common Directories

*/etc*

- Là 1 trong nhung thu muc go quan trong nhat trong he thong cua ban. Thư mục etc (viết tắt của etcetera) là vị trí phổ biến để lưu trữ các tệp hệ thống được hệ điều hành của bạn sử dụng.

- Ví dụ, tệp sudoers được đánh dấu trong ảnh chụp màn hình bên dưới chứa danh sách người dùng và nhóm có quyền chạy sudo hoặc một tập hợp lệnh với tư cách là người dùng root.

Ngoài ra, bên dưới còn có các tệp " passwd " và " shadow ". Hai tệp này đặc biệt dành cho Linux vì chúng hiển thị cách hệ thống của bạn lưu trữ mật khẩu cho từng người dùng theo định dạng được mã hóa gọi là sha512.

![image](https://github.com/user-attachments/assets/1ae00cf3-cf67-47c2-b7af-799ba31a5b42)

*/var*

Thư mục "/var", với "var" là viết tắt của dữ liệu biến, là một trong những thư mục gốc chính được tìm thấy trên bản cài đặt Linux . Thư mục này lưu trữ dữ liệu thường xuyên được truy cập hoặc ghi bởi các dịch vụ hoặc ứng dụng đang chạy trên hệ thống. Ví dụ, các tệp nhật ký từ các dịch vụ và ứng dụng đang chạy được ghi ở đây ( /var/log ), hoặc dữ liệu khác không nhất thiết phải liên kết với một người dùng cụ thể (tức là cơ sở dữ liệu và những thứ tương tự).

![image](https://github.com/user-attachments/assets/082e3509-01ee-480f-a3a2-f7d4d51e9655)

*/root*

Không giống như thư mục /home , thư mục /root  thực sự là home cho người dùng hệ thống "root". Không có gì hơn ở thư mục này ngoài việc chỉ hiểu rằng đây là thư mục home cho người dùng "root". Nhưng, điều này đáng được đề cập vì giả định hợp lý là người dùng này sẽ có dữ liệu của họ trong một thư mục như " /home/root " theo mặc định.  

![image](https://github.com/user-attachments/assets/6182975a-42e9-4d02-8429-898eacdde1fe)

*/tmp*

Đây là thư mục gốc duy nhất được tìm thấy trên bản cài đặt Linux. Viết tắt của " temporary ", thư mục /tmp là thư mục dễ bay hơi và được sử dụng để lưu trữ dữ liệu chỉ cần truy cập một hoặc hai lần. Tương tự như bộ nhớ trên máy tính của bạn, sau khi máy tính được khởi động lại, nội dung của thư mục này sẽ bị xóa.

Điều hữu ích cho chúng tôi trong pentesting là bất kỳ người dùng nào cũng có thể ghi vào thư mục này theo mặc định. Nghĩa là khi chúng tôi có quyền truy cập vào máy, nó sẽ là nơi tốt để lưu trữ những thứ như tập lệnh liệt kê của chúng tôi.

![image](https://github.com/user-attachments/assets/7c417461-b659-444f-af11-c05eb748bba3)


