## Chúng ta sẽ tìm hiểu về các mảng sau :

- Web Application Security

- Network Security

- Scripting

- Open Source Intelligence (OSINT)

- Defensive Security

## Trien khai may ao


- 1. Nhấp vào nút "Start AttackBox" màu xanh lam ở đầu phòng này. Là người dùng miễn phí, bạn chỉ có thể triển khai AttackBox trong 1 giờ mỗi ngày -  Đăng ký  để xóa giới hạn này.

- 2. Triển khai máy được hiển thị trong tác vụ này và đợi  1 phút  để cấu hình.

- 3. Sao chép IP của máy mà bạn đã triển khai trong tác vụ này.
 
- 4. Dán IP vào Firefox của máy AttackBox.
![image](https://github.com/user-attachments/assets/8deb7e0a-a777-40e7-9561-beb39c4cbd2e)

## Day 1 : WEB

Phương thức thường được sử dụng nhất để truy xuất thông tin được gọi là phương thức GET. Khi gửi dữ liệu đến máy chủ, phương thức phổ biến hơn là sử dụng phương thức có tên là POST.

Phong luyen web https://tryhackme.com/r/room/webfundamentals

HTTP có một nhược điểm cố hữu: cụ thể là nó không an toàn. Bất kỳ ai cũng có thể thấy những gì bạn yêu cầu và những gì được gửi lại cho bạn. Vì lý do này, HTTPS ( Hyper t ext Transfer Protocol S ecure ) đã được phát minh . Giao thức này hoạt động theo cùng một cách chính xác như HTTP chuẩn nhưng cung cấp kết nối được mã hóa (chức năng của nó vượt quá mức độ của hồ sơ này)

***Cookie***

Máy chủ nhận được yêu cầu của bạn với cookie đính kèm và kiểm tra cookie để xem bạn được phép truy cập ở mức nào. Sau đó, nó trả về phản hồi phù hợp với mức truy cập đó.


Ví dụ, người dùng chuẩn có thể thấy (nhưng không tương tác với) bảng điều khiển của chúng tôi; nhưng Santa có thể truy cập mọi thứ! Cookie cũng thường được sử dụng cho các mục đích khác như quảng cáo và lưu trữ tùy chọn của người dùng (ví dụ: chủ đề sáng/tối); tuy nhiên, điều này sẽ không quan trọng trong nhiệm vụ của bạn ngày hôm nay. Bất kỳ trang web nào cũng có thể đặt cookie với nhiều thuộc tính khác nhau -- quan trọng nhất trong số các thuộc tính này đối với nhiệm vụ hôm nay là tên và giá trị của cookie, cả hai đều sẽ luôn được đặt. Cần lưu ý rằng một trang web chỉ có thể truy cập cookie được liên kết với tên miền của riêng nó (tức là google.com không thể truy cập bất kỳ cookie nào được lưu trữ bởi tryhackme.com và ngược lại).

Điều quan trọng cần lưu ý là cookie được lưu trữ cục bộ trên máy tính của bạn . Điều này có nghĩa là chúng nằm trong tầm kiểm soát của bạn -- tức là bạn có thể thêm, chỉnh sửa hoặc xóa chúng theo ý muốn. Có một số cách để thực hiện việc này, tuy nhiên, cách phổ biến nhất là sử dụng Công cụ dành cho nhà phát triển trình duyệt của bạn, có thể truy cập trong hầu hết các trình duyệt bằng cách nhấn F12, hoặc Ctrl + Shift + I. Khi công cụ dành cho nhà phát triển mở, hãy điều hướng đến Storagetab trong FireFox hoặc Applicationtab trong Chrome/Edge và chọn Cookiesmenu ở phía bên trái của bảng điều khiển.

![image](https://github.com/user-attachments/assets/f28be414-3254-4509-a4f4-3cd28f275499)

Trong hình ảnh trên, bạn có thể thấy một cookie thử nghiệm cho một trang web. Các thuộc tính quan trọng "Name" và "Value" được hiển thị. Tên của cookie được sử dụng để nhận dạng cookie đó với máy chủ. Giá trị của cookie là dữ liệu được lưu trữ bởi máy chủ. Trong ví dụ này, máy chủ sẽ tìm kiếm một cookie có tên là "Cookie Name". Sau đó, nó sẽ truy xuất giá trị "CookieValue" từ cookie này.

Bạn có thể chỉnh sửa các giá trị này bằng cách nhấp đúp vào chúng. Tính năng này rất hữu ích nếu bạn có thể chỉnh sửa cookie phiên hoặc cookie ủy quyền, vì điều này có thể dẫn đến việc tăng quyền, giả sử bạn có quyền truy cập vào cookie ủy quyền của Quản trị viên.

Sau khi đọc xong hồ sơ dài dòng, bạn đã sẵn sàng để hack vào Trung tâm kiểm soát Giáng sinh của Ông già Noel! Bạn nhập địa chỉ IP ở đầu màn hình vào thanh tìm kiếm của trình duyệt và nhấn enter để tải trang.

![image](https://github.com/user-attachments/assets/c4861ab2-ff98-45ee-9d63-ae51cbba20fd)

![image](https://github.com/user-attachments/assets/c214648d-dfca-4c59-b019-ac5a7530a421)

![image](https://github.com/user-attachments/assets/e58ad761-ab91-4d63-9899-d78f6fb23610)

![image](https://github.com/user-attachments/assets/d27fe374-6f90-49d6-a68d-8012e6202b05)

![image](https://github.com/user-attachments/assets/a3a96e10-7a6e-4694-b46d-7590d53a8f5a)

LInk room https://tryhackme.com/r/room/learncyberin25days
