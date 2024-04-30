## Task 1 : What is HTTP(S)?

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/857a23a8-1cb8-4a9b-a119-ecd6a2bd2fa2)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/a3b09b7e-4b6d-4335-ae74-9b8d03162600)

Scheme: Hướng dẫn này sử dụng giao thức nào để truy cập tài nguyên như HTTP, HTTPS, FTP (Giao thức truyền tệp).

User:Some services require authentication to log in, you can put a username and password into the URL to log in.

Host: The domain name or IP address of the server you wish to access.

Port: The Port that you are going to connect to, usually 80 for HTTP and 443 for HTTPS, but this can be hosted on any port between 1 - 65535.

Path: The file name or location of the resource you are trying to access.

Query String: Extra bits of information that can be sent to the requested path. For example, /blog?id=1 would tell the blog path that you wish to receive the blog article with the id of 1.

Fragment: This is a reference to a location on the actual page requested. This is commonly used for pages with long content and can have a certain part of the page directly linked to it, so it is viewable to the user as soon as they access the page.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/1a60f392-9928-4458-99be-3241276192d0)

Gửi yêu cầu tới máy chủ web chỉ bằng dòng :

 "GET / HTTP/1.1"

 ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/e24f86e6-2f66-45c6-8413-75792eebd7ee)

Dòng 1: Yêu cầu này đang gửi phương thức GET (thông tin thêm về điều này trong tác vụ Phương thức HTTP), yêu cầu trang chủ có / và thông báo cho máy chủ web rằng chúng tôi đang sử dụng giao thức HTTP phiên bản 1.1.

Dòng 2: Chúng tôi nói với máy chủ web rằng chúng tôi muốn trang web tryhackme.com

Dòng 3: Chúng tôi thông báo với máy chủ web rằng chúng tôi đang sử dụng Trình duyệt Firefox phiên bản 87

Dòng 4: Chúng tôi đang thông báo với máy chủ web rằng trang web đã giới thiệu chúng tôi đến trang này là https://tryhackme.com

Dòng 5: Yêu cầu HTTP luôn kết thúc bằng một dòng trống để thông báo cho máy chủ web rằng yêu cầu đã kết thúc.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/f166a55f-ea40-4166-8575-ee71209ec36c)

Dòng 1: HTTP 1.1 là phiên bản của giao thức HTTP mà máy chủ đang sử dụng, sau đó là Mã trạng thái HTTP trong trường hợp này là "200 Ok" cho chúng tôi biết yêu cầu đã hoàn tất thành công.

Dòng 2: Dòng này cho chúng ta biết phần mềm máy chủ web và số phiên bản.

Dòng 3: Ngày, giờ và múi giờ hiện tại của máy chủ web.

Dòng 4: Tiêu đề Content-Type cho khách hàng biết loại thông tin nào sẽ được gửi, chẳng hạn như HTML, hình ảnh, video, pdf, XML.

Dòng 5: Độ dài nội dung cho khách hàng biết thời gian phản hồi là bao lâu, bằng cách này, chúng tôi có thể xác nhận không có dữ liệu nào bị thiếu.

Dòng 6: Phản hồi HTTP chứa một dòng trống để xác nhận việc kết thúc phản hồi HTTP.

Dòng 7-14: Thông tin đã được yêu cầu, trong trường hợp này là trang chủ.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/84197752-a348-476e-8532-da020265bd67)

## HTTP Methods

Phương thức HTTP là cách để khách hàng thể hiện hành động dự định của mình khi thực hiện yêu cầu HTTP. Có rất nhiều phương thức HTTP nhưng chúng tôi sẽ đề cập đến những phương thức phổ biến nhất, mặc dù phần lớn bạn sẽ xử lý phương thức GET và POST.

- GET Request

Điều này được sử dụng để ` Lấy thông tin ` từ một máy chủ web.

- POST Request

Điều này được sử dụng để ` gửi dữ liệu đến máy chủ web và có khả năng tạo bản ghi mới `

- PUT Request

Điều này được sử dụng để ` gửi dữ liệu đến máy chủ web để cập nhật thông tin `

- DELETE Request

Điều này được sử dụng để ` xóa thông tin/bản ghi khỏi máy chủ web. `

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/28103230-64ea-43de-83ca-21bc76cea430)

## TASK 4 : HTTP Status Codes

Trong nhiệm vụ trước, bạn đã biết rằng khi máy chủ HTTP phản hồi, dòng đầu tiên luôn chứa mã trạng thái thông báo cho máy khách về kết quả yêu cầu của họ và cả cách xử lý nó. Các mã trạng thái này có thể được chia thành 5 phạm vi khác nhau:

- 100-199 Phản hồi thông tin : Chúng được gửi để thông báo cho khách hàng biết phần đầu tiên trong yêu cầu của họ đã được chấp nhận và họ nên tiếp tục gửi phần còn lại của yêu cầu. Những mã này không còn phổ biến nữa.

- 200-299 Thành công : Dải mã trạng thái này được sử dụng để thông báo cho khách hàng rằng yêu cầu của họ đã thành công.

- 300-399 Chuyển hướng : Chúng được sử dụng để chuyển hướng yêu cầu của khách hàng đến một tài nguyên khác. Điều này có thể là một trang web khác hoặc một trang web khác hoàn toàn.

- 400-499 Lỗi máy khách : Được sử dụng để thông báo cho khách hàng rằng đã xảy ra lỗi với yêu cầu của họ.

- 500-599 Lỗi máy chủ : Điều này được dành riêng cho các lỗi xảy ra ở phía máy chủ và thường chỉ ra một vấn đề khá lớn với việc máy chủ xử lý yêu cầu.

Common HTTP Status Codes:

Có rất nhiều mã trạng thái HTTP khác nhau và điều đó chưa bao gồm thực tế là các ứng dụng thậm chí có thể tự xác định mã trạng thái của chúng, chúng ta sẽ xem xét các phản hồi HTTP phổ biến nhất mà bạn có thể gặp:

- 200 - OK Yêu cầu đã được hoàn thành thành công.

- 201 - Đã tạo Một tài nguyên đã được tạo (ví dụ: người dùng mới hoặc bài đăng blog mới)

- 301 - Đã di chuyển vĩnh viễn Điều này chuyển hướng trình duyệt của khách hàng đến một trang web mới hoặc thông báo cho các công cụ tìm kiếm rằng trang đó đã được di chuyển đi nơi khác và thay vào đó hãy tìm ở đó.

- 302 - Found Tương tự như chuyển hướng vĩnh viễn ở trên, nhưng như tên cho thấy, đây chỉ là thay đổi tạm thời và nó có thể thay đổi lần nữa trong tương lai gần.

- 400 - Yêu cầu không hợp lệ Điều này cho trình duyệt biết rằng có điều gì đó sai hoặc thiếu trong yêu cầu của họ. Điều này đôi khi có thể được sử dụng nếu tài nguyên máy chủ web đang được yêu cầu mong đợi một tham số nhất định mà máy khách không gửi.

- 401 - Không được ủy quyền Bạn hiện không được phép xem tài nguyên này cho đến khi bạn đã ủy quyền với ứng dụng web, phổ biến nhất là bằng tên người dùng và mật khẩu.

- 403 - Bị cấm Bạn không có quyền xem tài nguyên này cho dù bạn có đăng nhập hay không.

- 405 - Phương thức không được phép Tài nguyên không cho phép yêu cầu phương thức này, ví dụ: bạn gửi yêu cầu GET tới tài nguyên /tạo tài khoản khi thay vào đó nó đang mong đợi một yêu cầu POST.

- 404 - Không tìm thấy trang Trang/tài nguyên bạn yêu cầu không tồn tại.

- 500 - Lỗi dịch vụ nội bộ Máy chủ đã gặp phải một số loại lỗi với yêu cầu của bạn mà nó không biết cách xử lý đúng cách.

-Lỗi 503: Dịch vụ không khả dụng Máy chủ này không thể xử lý yêu cầu của bạn vì nó bị quá tải hoặc ngừng hoạt động để bảo trì.


![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/f9e21900-7883-4e6a-9919-3fa841002574)


https://tryhackme.com/r/room/httpindetail
