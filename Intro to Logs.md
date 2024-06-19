### Introduction to Logs

Chúng ta sử dụng Logs để làm gì? Để lưu lại lịch sử các hoạt động từ đó củng cố tình hình bảo mật và bảo về tài sản kỹ thuật số của mình hiệu quả hơn.

Để có thể kiểm tra thủ công được bạn cần nắm bắt được sự phức tạp của phân tích nhật ký và làm quen với các công cụ và kỹ thuật có sẵn. Các công cụ và phương pháp phân tích nhật ký trao quyeenf cho các bạn giải thích các sự kiện và thiết lập nguồn bằng chứng lịch sử đáng tin cậy.

-> Cần biết cách sử dụng nhật lý để ghi lại hành động của đối thủ, các công cụ và kỹ thuật cần thiết để thực hiện phân tích nhật ký.


### Working with Logs: Scenario (kịch bản)

- Scenario : Máy chủ web của SwiftSpend Financial liên tục bị tấn công bởi các bản quét từ đối thủ. Với tư cách là quản trị viên hệ thống của tổ chức này được giao nhiệm vụ giải quyết tình trạng khó khăn này, bạn phải xác định xem đối thủ đang làm gì bằng cách định cấu hình ghi nhật ký và phân tích nhật ký được thu thập.

- QUAN TRỌNG: Người dùng damianhall có các đặc quyền sudo hạn chế. Ra lệnh sudo -l để kiểm tra xem người dùng này có thể chạy lệnh nào. Những lệnh giới hạn này là tất cả những gì cần thiết để hoàn thành các nhiệm vụ tiếp theo.

> Sudo -l : kiểm tra xem người dùng này có thể chạy lệnh nào

-  A digital log sẽ cung cấp bản ghi lịch sử về hoạt động của hệ thống.

-  Trong thế giới kỹ thuật số, mọi tương tác với hệ thống máy tính – từ nỗ lực xác thực, cấp quyền, truy cập tệp và kết nối với mạng cho đến gặp lỗi hệ thống sẽ luôn để lại dấu chân kỹ thuật số dưới dạng nhật ký

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/b1945913-f3af-4471-acac-0a2b75e2003b)

- Những bản ghi này cung cấp thông tin chi tiết về những gì hệ thống đã và đang thực hiện, ghi lại một loạt các sự kiện như thông tin đăng nhập của người dùng, tệp truy cập, lỗi hệ thống, kết nối mạng và thay đổi dữ liệu hoặc cấu hình hệ thống.

- Log sẽ bao gồm : 1. Thời gian khi 1 sự kiện được ghi lại

                   2.Tên của hệ thống hoặc ứng dụng đã tạo mục nhập nhật ký

                   3. Loại sự kiện xảy ra

                   4. Thông tin chi tiết bổ sung về sự kiện, chẳng hạn như người dùng đã bắt đầu sự kiện hoặc địa chỉ IP của thiết bị đã tạo ra sự kiện

  - Do các tương tác kỹ thuật diễn ra liên tục và có nhịp độ nhanh nên kích thước của tập nhật ký có thể tăng theo cấp sooss nhân tùy thuộc các hoạt động được ghi tren hệ thống

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/24a3f5ac-ad0d-41d7-9c65-50f0c1e8667f)

https://tryhackme.com/r/room/introtologs


