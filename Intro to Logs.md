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

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/a3517984-2fc2-4806-9c15-9f1b77d7164c)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/b169c8cf-4861-41ee-b2a7-b9b055165d30)

### Cac loai Logs

Nhật ký ứng dụng: Thông báo về các ứng dụng cụ thể, bao gồm trạng thái, lỗi, cảnh báo, v.v.

Nhật ký kiểm tra: Các hoạt động liên quan đến quy trình vận hành quan trọng đối với việc tuân thủ quy định.

Nhật ký bảo mật: Các sự kiện bảo mật như thông tin đăng nhập, thay đổi quyền, hoạt động tường lửa, v.v.

Nhật ký máy chủ: Các nhật ký khác nhau mà máy chủ tạo ra, bao gồm nhật ký hệ thống, sự kiện, lỗi và truy cập.

Nhật ký hệ thống: Hoạt động hạt nhân, lỗi hệ thống, trình tự khởi động và trạng thái phần cứng.

Nhật ký mạng: Lưu lượng mạng, kết nối và các sự kiện khác liên quan đến mạng.

Nhật ký cơ sở dữ liệu: Các hoạt động trong hệ thống cơ sở dữ liệu, chẳng hạn như truy vấn và cập nhật.

Nhật ký máy chủ web: Các yêu cầu được xử lý bởi máy chủ web, bao gồm URL, mã phản hồi, v.v.

### Dinh dang nhat ky

- Định dạng nhật ký xác định cấu trúc và tổ chức dữ liệu trong tệp nhật ký. Nó chỉ định cách mã hóa dữ liệu, cách mỗi mục nhập được phân cách và những trường nào được bao gồm trong mỗi hàng. Các định dạng này có thể rất khác nhau và có thể thuộc ba loại chính: Bán cấu trúc, Có cấu trúc và Không cấu trúc. Chúng ta sẽ khám phá những danh mục này và minh họa cách sử dụng chúng bằng các ví dụ.

     + Nhật ký bán cấu trúc: Những nhật ký này có thể chứa dữ liệu có cấu trúc và không cấu trúc, với các thành phần có thể dự đoán được chứa văn bản dạng tự do. Những ví dụ bao gồm:
 
          * Định dạng thông báo nhật ký hệ thống: Một giao thức ghi nhật ký được áp dụng rộng rãi cho nhật ký hệ thống và mạng.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/c734ec41-0064-4303-aaaa-0f89a8074af5)

            * Định dạng Nhật ký sự kiện Windows ( EVTX ): Nhật ký độc quyền của Microsoft dành cho hệ thống Windows.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/1def24ee-a8c1-4128-a9a0-ce228b949a16)

    + Nhật ký có cấu trúc: Tuân theo định dạng nghiêm ngặt và tiêu chuẩn hóa, những nhật ký này có lợi cho việc phân tích và phân tích. Các định dạng nhật ký có cấu trúc điển hình bao gồm:

          * Định dạng được phân tách bằng trường: Giá trị được phân tách bằng dấu phẩy (CSV) và Giá trị được phân tách bằng tab (TSV) là các định dạng thường được sử dụng cho dữ liệu dạng bảng.

  ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/8321fe79-55e1-4841-9667-6aa06b287c36)

         * Ký hiệu đối tượng JavaScript ( JSON ): Được biết đến với khả năng đọc và tương thích với các ngôn ngữ lập trình hiện đại.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/363e999a-f71a-4a38-8643-6c9ec0868af1)

        * Định dạng nhật ký mở rộng W3C (ELF): Được xác định bởi World Wide Web Consortium (W3C), có thể tùy chỉnh để ghi nhật ký máy chủ web. Nó thường được sử dụng bởi Máy chủ Web Dịch vụ Thông tin Internet (IIS) của Microsoft.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/888f1674-f8ef-495a-ac2f-e90f9733cce7)


![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/07ea09c5-428c-4521-84e2-7b96cec6ba15)


![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/19ef2cf6-c121-4024-80aa-b0a1d577f350)

### Tiêu chuẩn nhật ký

- Tiêu chuẩn nhật ký là một bộ hướng dẫn hoặc thông số kỹ thuật xác định cách tạo, truyền và lưu trữ nhật ký. Các tiêu chuẩn nhật ký có thể chỉ định việc sử dụng các định dạng nhật ký cụ thể nhưng chúng cũng bao gồm các khía cạnh khác của việc ghi nhật ký, chẳng hạn như những sự kiện nào cần được ghi lại, cách truyền nhật ký một cách an toàn và thời gian lưu giữ nhật ký. Ví dụ về các tiêu chuẩn nhật ký bao gồm:

- Biểu thức sự kiện chung (CEE): Tiêu chuẩn này doMITER, cung cấp cấu trúc chung cho dữ liệu nhật ký, giúp tạo, truyền, lưu trữ và phân tích nhật ký dễ dàng hơn.

- Bảng ghi nhật ký OWASP : Hướng dẫn dành cho nhà phát triển xây dựng cơ chế ghi nhật ký ứng dụng, đặc biệt liên quan đến ghi nhật ký bảo mật.

- Giao thức nhật ký hệ thống: Syslog là một tiêu chuẩn để ghi nhật ký tin nhắn, cho phép tách phần mềm tạo tin nhắn khỏi hệ thống lưu trữ chúng và phần mềm báo cáo và phân tích chúng.

- Ấn bản đặc biệt của NIST 800-92: Ấn phẩm này hướng dẫn quản lý nhật ký bảo mật máy tính.

- Nhật ký giám sát Azure: Hướng dẫn giám sát nhật ký trên Microsoft Azure.

- Ghi nhật ký trên Google Cloud: Nguyên tắc đăng nhập trên Google Cloud Platform (GCP).

- Ghi nhật ký cơ sở hạ tầng đám mây của Oracle: Hướng dẫn đăng nhập vào Cơ sở hạ tầng đám mây của Oracle (OCI).

- Virginia Tech - Tiêu chuẩn ghi nhật ký công nghệ thông tin: Đánh giá nhật ký mẫu và hướng dẫn tuân thủ.

