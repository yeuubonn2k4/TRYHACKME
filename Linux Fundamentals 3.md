## 3. Trinh soan thao van ban Terminal

Trong suốt loạt bài này, chúng ta chỉ lưu trữ văn bản trong các tệp bằng cách kết hợp lệnh echovà toán tử đường ống ( >và >>). Đây không phải là cách hiệu quả để xử lý dữ liệu khi bạn làm việc với các tệp có nhiều dòng và các loại

**Giới thiệu trình soạn thảo văn bản đầu cuối**

Có một số tùy chọn mà bạn có thể sử dụng, tất cả đều có nhiều tính thân thiện và tiện ích. Nhiệm vụ này sẽ giới thiệu cho bạn nanonhưng cũng cho bạn thấy một giải pháp thay thế có tên VIM(mà TryHackMe có một phòng dành riêng!)

Nano

Thật dễ dàng để bắt đầu với Nano! Để tạo hoặc chỉnh sửa tệp bằng nano, chúng ta chỉ cần sử dụng nano filename-- thay thế "filename" bằng tên tệp bạn muốn chỉnh sửa.

![image](https://github.com/user-attachments/assets/2e45ebf3-10a2-47c6-8deb-dc23c0b25ea7)

Khi chúng ta nhấn enter để thực hiện lệnh, nanosẽ khởi chạy! Nơi chúng ta có thể bắt đầu nhập hoặc sửa đổi văn bản của mình. Bạn có thể điều hướng từng dòng bằng phím mũi tên "lên" và "xuống" hoặc bắt đầu một dòng mới bằng phím "Enter" trên bàn phím.

![image](https://github.com/user-attachments/assets/16c3eaf7-ed93-4757-a3ee-79f489129bd7)

VIM

VIM là trình soạn thảo văn bản tiên tiến hơn nhiều. Mặc dù bạn không cần phải biết tất cả các tính năng nâng cao, nhưng việc đề cập đến nó sẽ hữu ích để nâng cao kỹ năng Linux của bạn .

![image](https://github.com/user-attachments/assets/c12d829d-fc22-4713-ae4a-9356278cee6d)

Một số lợi ích của VIM, mặc dù mất nhiều thời gian hơn để làm quen, bao gồm:

Có thể tùy chỉnh -  bạn có thể sửa đổi  các phím tắt theo ý muốn của mình

Tô sáng cú pháp - tính năng này hữu ích nếu bạn đang viết hoặc bảo trì mã, khiến nó trở thành lựa chọn phổ biến cho các nhà phát triển phần mềm

VIM hoạt động trên tất cả các thiết bị đầu cuối mà nano có thể không được cài đặt

Có rất nhiều tài nguyên như tài liệu hướng dẫn , hướng dẫn và các loại tài liệu khác có sẵn để bạn sử dụng.

TryHackMe có một phòng giới thiệu VIM nếu bạn muốn tìm hiểu thêm về trình soạn thảo này!

### Tai lieu Vim https://vim.rtorr.com/

Sau khi `nano task3` ta duoc

![image](https://github.com/user-attachments/assets/aef7f71e-9524-40c5-b40e-772c791f8907)

![image](https://github.com/user-attachments/assets/a792f3b3-0151-4018-a576-dcb31e8a0a77)

## 4. Tien ich chung/ huu ich

- *Tai xuong tep (Wget)*

Một tính năng khá cơ bản của máy tính là khả năng chuyển tệp. Ví dụ, bạn có thể muốn tải xuống một chương trình, một tập lệnh hoặc thậm chí là một hình ảnh. May mắn thay, có nhiều cách để chúng ta có thể truy xuất các tệp này.

 Chúng ta sẽ tìm hiểu cách sử dụng wget . Lệnh này cho phép chúng ta tải xuống các tệp từ web qua HTTP -- như thể bạn đang truy cập tệp trong trình duyệt của mình. Chúng ta chỉ cần cung cấp địa chỉ của tài nguyên mà chúng ta muốn tải xuống. Ví dụ, nếu tôi muốn tải xuống một tệp có tên "myfile.txt" vào máy của mình, giả sử tôi biết địa chỉ web của tệp đó -- thì nó sẽ trông giống như thế này:

wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt

- *Chuyển tập tin từ máy chủ của bạn - SCP ( SSH )*

Secure copy, hay SCP, chỉ là một phương tiện sao chép tệp an toàn. Không giống như lệnh cp thông thường, lệnh này cho phép bạn chuyển tệp giữa hai máy tính bằng giao thức SSH để cung cấp cả xác thực và mã hóa.

Khi làm việc trên mô hình NGUỒN và ĐẾN, SCP cho phép bạn:

Sao chép các tập tin và thư mục từ hệ thống hiện tại của bạn sang hệ thống từ xa

Sao chép các tập tin và thư mục từ hệ thống từ xa vào hệ thống hiện tại của bạn

Với điều kiện là chúng ta biết tên người dùng và mật khẩu của người dùng trên hệ thống hiện tại của bạn và người dùng trên hệ thống từ xa. Ví dụ, hãy sao chép một tệp ví dụ từ máy của chúng ta sang máy từ xa, mà tôi đã trình bày gọn gàng trong bảng bên dưới:

![image](https://github.com/user-attachments/assets/00b3d71f-f749-440a-9b21-97f38704d2de)

Phục vụ các tập tin từ máy chủ của bạn - WEB

- Máy Ubuntu được đóng gói sẵn python3. Python cung cấp một mô-đun nhẹ và dễ sử dụng có tên là "HTTPServer". Mô-đun này biến máy tính của bạn thành một máy chủ web nhanh chóng và dễ dàng mà bạn có thể sử dụng để phục vụ các tệp của riêng mình, sau đó chúng có thể được tải xuống bằng máy tính khác bằng các lệnh như curl và wget. 

"HTTPServer" của Python3 sẽ phục vụ các tệp trong thư mục nơi bạn chạy lệnh, nhưng điều này có thể thay đổi bằng cách cung cấp các tùy chọn có thể tìm thấy trong các trang hướng dẫn. Đơn giản, tất cả những gì chúng ta cần làm là chạy python3 -m  http.server trong terminal để khởi động mô-đun! Trong đoạn trích bên dưới, chúng ta đang phục vụ từ một thư mục có tên là "webserver", có một tên duy nhất là "file".

![image](https://github.com/user-attachments/assets/4ee66c2a-702c-4fc9-9732-72e6b8d9dac5)

Bây giờ, hãy sử dụng wget để tải xuống tệp bằng địa chỉ MACHINE_IP và tên tệp. Hãy nhớ rằng, vì máy chủ python3 đang chạy cổng 8000, bạn sẽ cần chỉ định điều này trong lệnh wget của mình. Ví dụ:

![image](https://github.com/user-attachments/assets/47f508a4-6dce-4bdd-9954-987aa8c34015)

Lưu ý, bạn sẽ cần mở một terminal mới để sử dụng wgetvà giữ nguyên terminal mà bạn đã dùng để khởi động máy chủ web Python3. Lý do là vì sau khi bạn khởi động máy chủ web Python3, nó sẽ chạy trong terminal đó cho đến khi bạn hủy.

Chúng ta hãy cùng xem đoạn trích dưới đây làm ví dụ:

![image](https://github.com/user-attachments/assets/248508f9-4f03-4027-8017-2cfd48fbd156)

Hãy nhớ rằng , bạn sẽ cần chạy lệnh wget trong một terminal khác (trong khi vẫn giữ terminal đang chạy máy chủ Python3 hoạt động). Một ví dụ về điều này trên TryHackMe AttackBox như sau:

![image](https://github.com/user-attachments/assets/c3c0da52-4b6a-44a7-97ce-a75a59550e79)

Một nhược điểm của module này là bạn không có cách nào để lập chỉ mục, vì vậy bạn phải biết tên chính xác và vị trí của tệp mà bạn muốn sử dụng. Đây là lý do tại sao tôi thích sử dụng Updog. Updog là gì ? Một máy chủ web tiên tiến hơn nhưng nhẹ hơn. Nhưng hiện tại, chúng ta hãy sử dụng "Máy chủ HTTP" của Python.

![image](https://github.com/user-attachments/assets/6ffc0bf0-7f0c-4a4d-980d-72e7a11f9cdd)

## 5. Quy trinh 101

- Xem cac quy trinh

Chúng ta có thể sử dụng lệnh thân thiện này psđể cung cấp danh sách các tiến trình đang chạy dưới dạng phiên của người dùng và một số thông tin bổ sung như mã trạng thái, phiên đang chạy tiến trình đó, thời gian sử dụng CPU mà tiến trình đó đang sử dụng và tên của chương trình hoặc lệnh thực tế đang được thực thi:

![image](https://github.com/user-attachments/assets/6f0c7dc7-4818-4f70-9ce7-e9d86ce9ab58)

Lưu ý rằng trong ảnh chụp màn hình ở trên, tiến trình thứ hai ps có PID là 204, sau đó trong lệnh bên dưới, PID này được tăng lên 205.

Để xem các tiến trình do người dùng khác chạy và các tiến trình không chạy từ phiên (tức là tiến trình hệ thống), chúng ta cần cung cấp aux cho pslệnh như sau:ps aux

![image](https://github.com/user-attachments/assets/a4baa7ec-e26f-408e-8d92-655674888980)

? Lưu ý chúng ta có thể thấy tổng cộng 5 quy trình -- lưu ý cách chúng ta hiện có "root" và "cmnatic"

Một lệnh rất hữu ích khác là lệnh top; top cung cấp cho bạn số liệu thống kê thời gian thực về các tiến trình đang chạy trên hệ thống của bạn thay vì chế độ xem một lần. Các số liệu thống kê này sẽ làm mới sau mỗi 10 giây, nhưng cũng sẽ làm mới khi bạn sử dụng các phím mũi tên để duyệt qua các hàng khác nhau. Một lệnh tuyệt vời khác để có được cái nhìn sâu sắc về hệ thống của bạn là thông qua toplệnh

Quản lý quy trình

Bạn có thể gửi tín hiệu để chấm dứt các tiến trình; có nhiều loại tín hiệu tương quan với mức độ "sạch" mà tiến trình được xử lý bởi kernel. Để hủy một lệnh, chúng ta có thể sử dụng lệnh có tên phù hợp kill và PID liên quan mà chúng ta muốn hủy. Ví dụ, để hủy PID 1337, chúng ta sẽ sử dụng kill 1337.

- Dưới đây là một số tín hiệu mà chúng ta có thể gửi đến một tiến trình khi nó bị tắt:

SIGTERM - Giết tiến trình, nhưng cho phép nó thực hiện một số tác vụ dọn dẹp trước

SIGKILL - Giết tiến trình - không thực hiện bất kỳ dọn dẹp nào sau đó

SIGSTOP - Dừng/tạm dừng một tiến trình

#### Quá trình bắt đầu như thế nào?

Hãy bắt đầu bằng cách nói về không gian tên. Hệ điều hành ( OS ) sử dụng không gian tên để cuối cùng chia nhỏ các tài nguyên có sẵn trên máy tính thành các quy trình (như CPU , RAM và mức độ ưu tiên). Hãy nghĩ về việc chia máy tính của bạn thành các lát cắt -- tương tự như một chiếc bánh. Các quy trình trong lát cắt đó sẽ có quyền truy cập vào một lượng sức mạnh tính toán nhất định, tuy nhiên, đó sẽ là một phần nhỏ trong số những gì thực sự có sẵn cho mọi quy trình nói chung.

Không gian tên rất tốt cho bảo mật vì đây là cách cô lập các quy trình với nhau -- chỉ những quy trình nằm trong cùng một không gian tên mới có thể nhìn thấy nhau.

Trước đây chúng ta đã nói về cách PID hoạt động và đây là nơi nó phát huy tác dụng. Tiến trình có ID là 0 là tiến trình được bắt đầu khi hệ thống khởi động. Tiến trình này là init của hệ thống trên Ubuntu, chẳng hạn như systemd , được sử dụng để cung cấp cách quản lý các tiến trình của người dùng và nằm giữa hệ điều hành và người dùng. 

Ví dụ, sau khi hệ thống khởi động và khởi tạo, systemd là một trong những tiến trình đầu tiên được khởi động. Bất kỳ chương trình hoặc phần mềm nào mà chúng ta muốn khởi động sẽ khởi động như cái được gọi là tiến trình con của systemd . Điều này có nghĩa là nó được systemd kiểm soát , nhưng sẽ chạy như một tiến trình riêng của nó (mặc dù chia sẻ tài nguyên từ systemd ) để giúp chúng ta dễ dàng xác định và những thứ tương tự.

![image](https://github.com/user-attachments/assets/8723314a-0e11-4766-a98f-8d647adbeb87)

Bắt đầu các quy trình/dịch vụ khi khởi động

Một số ứng dụng có thể được khởi động khi khởi động hệ thống mà chúng ta sở hữu. Ví dụ, máy chủ web, máy chủ cơ sở dữ liệu hoặc máy chủ truyền tệp. Phần mềm này thường rất quan trọng và thường được quản trị viên yêu cầu khởi động trong quá trình khởi động hệ thống.

Trong ví dụ này, chúng ta sẽ yêu cầu máy chủ web Apache khởi động Apache theo cách thủ công và sau đó yêu cầu hệ thống chạy Apache2 khi khởi động.

Nhập lệnh systemctl-- lệnh này cho phép chúng ta tương tác với tiến trình/daemon systemd . Tiếp tục với ví dụ của chúng tôi, systemctl là lệnh dễ sử dụng có định dạng sau:systemctl [option] [service]

Ví dụ, để bảo apache khởi động, chúng ta sẽ sử dụng systemctl start apache2. Có vẻ đơn giản, đúng không? Tương tự như nếu chúng ta muốn dừng apache, chúng ta chỉ cần thay thế [option]bằng stop (thay vì start như chúng tôi đã cung cấp)

Chúng ta có thể thực hiện bốn lựa chọn với systemctl:

- Bắt đầu

- Dừng lại

- Cho phép

- Vô hiệu hóa

Giới thiệu về Backgrounding và  Foregrounding  trong Linux

Các tiến trình có thể chạy ở hai trạng thái: Trong nền và trong tiền cảnh. Ví dụ, các lệnh bạn chạy trong terminal của mình như "echo" hoặc những thứ tương tự sẽ chạy trong tiền cảnh của terminal của bạn vì đó là lệnh duy nhất được cung cấp mà không được yêu cầu chạy trong nền. "Echo" là một ví dụ tuyệt vời vì đầu ra của echo sẽ trả về cho bạn trong tiền cảnh, nhưng sẽ không chạy trong nền - hãy xem ảnh chụp màn hình bên dưới, chẳng hạn.

Chúng ta có thể làm chính xác như vậy khi thực hiện những thứ như tập lệnh -- thay vì dựa vào toán tử &, chúng ta có thể sử dụng Ctrl + Ztrên bàn phím để làm nền cho một tiến trình. Đây cũng là một cách hiệu quả để "tạm dừng" việc thực hiện một tập lệnh hoặc lệnh như trong ví dụ dưới đây:

![image](https://github.com/user-attachments/assets/db99b86b-e77d-4cd0-83db-0b84121031c4)

Làm nổi bật một quá trình

Bây giờ chúng ta có một tiến trình đang chạy ở chế độ nền, ví dụ như tập lệnh "background.sh" có thể được xác nhận bằng lệnh ps aux , chúng ta có thể quay lại và đưa tiến trình này trở lại chế độ nền để tương tác.

![image](https://github.com/user-attachments/assets/8f7fe04d-afbe-4d97-9956-903db2db42d0)

Với tiến trình nền của chúng ta sử dụng một trong hai Ctrl + Ztoán &tử, chúng ta có thể sử dụng fgđể đưa tiến trình này trở lại tiêu điểm như bên dưới, trong đó chúng ta có thể thấy lệnh fgđang được sử dụng để đưa tiến trình nền trở lại sử dụng trên thiết bị đầu cuối, tại đó đầu ra của tập lệnh hiện được trả về cho chúng ta.

![image](https://github.com/user-attachments/assets/c062ec42-e854-415c-8ece-1d5070b8ba09)

