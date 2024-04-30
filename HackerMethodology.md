Methodology Outline Phuongg phaps luan hoc
The Process that pentesters follow is summarized in the following steps:

Reconnaissance // trinh sat

Enumeration/Scanning // dem quet

Gaining Access // dat duoc quyen truy cap

Privilege Escalation // nang cao dac quyen

Covering Tracks // tracks tat ca

Reporting // bao cao

Reconnaissance Overview
There are some specialized tools that we can utilize but for this introduction, it is good to know the following tools.

Google (specifically Google Dorking) Wikipedia PeopleFinder.com who.is sublist3r hunter.io builtwith.com wappalyzer

Search for subdomains of kali.org (-d kali.org) using the Bing search engine (-e bing) with 3 threads (-t 3). Tìm kiếm subdomain của kali.org (-d kali.org) bằng công cụ tìm kiếm Bing (-e bing) với 3 luồng (-t 3).

Who is the CEO of SpaceX?

-> Elon Musk

Do some research into the tool: sublist3r, what does it list?

-> subdomains

What is it called when you use Google to look for specific vulnerabilities or to research a specific topic of interest?

-> Google Dorking

https://www.kali.org/tools/sublist3r/

Enumeration and Scanning Overview
Đây là nơi hacker sẽ bắt đầu tương tác (quét và liệt kê) mục tiêu để cố gắng tìm ra các lỗ hổng liên quan đến mục tiêu.

Đây là nơi các công cụ chuyên dụng hơn bắt đầu được đưa vào kho vũ khí. Các công cụ như nmap, dirb, metasploit, mining-db, Burp Suite và các công cụ khác rất hữu ích để giúp chúng tôi cố gắng tìm ra các lỗ hổng trong mục tiêu

Trong giai đoạn quét và liệt kê, kẻ tấn công tương tác với mục tiêu để xác định bề mặt tấn công tổng thể của nó.

Bề mặt tấn công xác định mục tiêu có thể dễ bị tổn thương trong giai đoạn Khai thác. Những lỗ hổng này có thể là một loạt các thứ.Những lỗ hổng này có thể là nhiều thứ: bất kỳ thứ gì từ một trang web không được khóa đúng cách, một trang web rò rỉ thông tin, SQL Insert, Cross Site Scripting hoặc bất kỳ lỗ hổng nào khác.

-> Để đơn giản hóa - giai đoạn liệt kê và quét là nơi chúng tôi sẽ cố gắng xác định mục tiêu có thể dễ bị tổn thương.

Ví dụ: một công cụ quan trọng trong kho vũ khí của chúng tôi là công cụ có tên Nmap (Tôi khuyên bạn nên kiểm tra phòng nmap sau khi bạn hoàn thành phòng này).

Cach tim port: netstat -a -b -n

Cach tim bang google: google.com: port_number;

ví dụ: chỉ nói FTP (Giao thức truyền tệp) là không đủ,nmap có thể cố gắng lấy dấu vân tay và xác định PHIÊN BẢN chính xác của FTP, điều này có thể cho phép chúng tôi tìm ra lỗ hổng cụ thể trong mục tiêu

dirb (được sử dụng để tìm các thư mục có tên thông dụng trên một trang web - giống như trong https://www.tesla.com cũng cóhttps://www.tesla.com/about, https://www.tesla.com/model3, https://www.tesla.com/modely, and most importantly https://www.tesla.com/models WITH LUDICROUS MODE!! ♥)

dirbuster (tương tự dirb nhưng có tên hay hơn và có giao diện người dùng)

enum4linux (công cụ được sử dụng riêng cho Linux để tìm lỗ hổng)

metasploit (công cụ này chủ yếu được sử dụng để khai thác, nhưng nó cũng được tích hợp sẵn một số công cụ liệt kê)

Burp Suite (công cụ này có thể được sử dụng để quét một trang web để tìm các thư mục con và chặn lưu lượng truy cập mạng)

What does enumeration help to determine about the target?

-> Attack Surface

Do some reconnaissance about the tool: Metasploit, what company developed it?

-> Rapid7

What company developed the technology behind the tool Burp Suite?

-> Portswigger

Exploitation
Giai đoạn khai thác chỉ có thể tốt bằng các giai đoạn điều tra và liệt kê trước đó, nếu không liệt kê hết tất cả các lỗ hổng, bạn có thể bỏ lỡ cơ hội,hoặc nếu bạn không xem xét kỹ mục tiêu - cách khai thác bạn đã chọn có thể thất bại hoàn toàn!

Một công cụ phổ biến được sử dụng để khai thác có tên là Metasploit, có nhiều tập lệnh cài sẵn nhằm cố gắng giữ cho cuộc sống trở nên đơn giản.

Bạn cũng có thể sử dụng các công cụ như Burp Suite và SQLMap để khai thác các ứng dụng web. Có các công cụ như msfvenom (để xây dựng tải trọng tùy chỉnh), BeEF (khai thác dựa trên trình duyệt) và nhiều công cụ khác.

nhớ rằng người kiểm tra thâm nhập chuyên nghiệp không bao giờ nhảy vào giai đoạn khai thác mà không thực hiện khảo sát và liệt kê đầy đủ.

What is one of the primary exploitation tools that pentester(s) use?

-> metasploit

Privilege Escalation
Sau khi chúng tôi có được quyền truy cập vào máy nạn nhân thông qua giai đoạn khai thác, bước tiếp theo là chuyển đặc quyền lên tài khoản người dùng cao hơn

Privilege escalation can take many, many forms, some examples are:

Cracking password hashes found on the target // Bẻ khóa mật khẩu được tìm thấy trên mục tiêu

Finding a vulnerable service or version of a service which will allow you to escalate privilege THROUGH the service // Tìm một dịch vụ hoặc phiên bản dễ bị tấn công của dịch vụ sẽ cho phép bạn nâng cấp đặc quyền QUA dịch vụ

Password spraying of previously discovered credentials (password re-use) //Quét mật khẩu của thông tin xác thực được phát hiện trước đó (sử dụng lại mật khẩu)

Using default credentials // Sử dụng thông tin xác thực mặc định

Finding secret keys or SSH keys stored on a device which will allow pivoting to another machine // Tìm khóa bí mật hoặc khóa SSH được lưu trữ trên thiết bị sẽ cho phép chuyển sang máy khác

Running scripts or commands to enumerate system settings like 'ifconfig' to find network settings, or the command 'find / -perm -4000 -type f 2>/dev/null' to see if the user has access to any commands they can run as root //Chạy các tập lệnh hoặc lệnh để liệt kê các cài đặt hệ thống như “ifconfig” để tìm cài đặt mạng hoặc lệnh “find/-perm -4000 -type f 2>/dev/null' để xem liệu người dùng có quyền truy cập vào bất kỳ lệnh nào mà họ có thể chạy bằng root không

-> Leo thang đặc quyền

In Windows what is usually the other target account besides Administrator?

-> system

What thing related to SSH could allow you to login to another machine (even without knowing the username or password)?

-> keys

Covering Tracks: Truy tìm dấu vết
Bạn phải luôn có sự cho phép rõ ràng từ chủ sở hữu hệ thống về thời điểm thử nghiệm diễn ra, cách thức diễn ra và phạm vi mục tiêu trong bất kỳ thử nghiệm thâm nhập nào.

Vì các quy tắc tham gia cho thử nghiệm thâm nhập phải được thống nhất trước khi thử nghiệm diễn ra, nên người thử nghiệm thâm nhập phải dừng NGAY LẬP TỨC khi họ đã đạt được mức tăng đặc quyền và báo cáo kết quả phát hiện cho khách hàng.

Tuy nhiên, ngay cả khi bạn không che giấu dấu vết của mình, điều này không giải quyết được trách nhiệm pháp lý của bạn đối với việc khai thác của bạn. Thông thường bạn sẽ cần hỗ trợ Quản trị viên CNTT hoặc chủ sở hữu hệ thống trong việc dọn sạch mã khai thác mà bạn đã sử dụng, đồng thời đề xuất CÁCH ngăn chặn cuộc tấn công trong tương lai.

Mặc dù các tin tặc có đạo đức hiếm khi có nhu cầu che giấu dấu vết của mình nhưng bạn vẫn phải theo dõi và ghi chú cẩn thận tất cả các nhiệm vụ mà bạn đã thực hiện trong quá trình kiểm tra thâm nhập để hỗ trợ sửa lỗi.các lỗ hổng và đề xuất các thay đổi cho chủ sở hữu hệ thống.

Report
The reporting phase often includes the following things:

The Finding(s) or Vulnerabilities // (Các) Phát hiện hoặc Lỗ hổng

The CRITICALITY of the Finding // Tính quan trọng của việc phát hiện

A description or brief overview of how the finding was discovered // Mô tả hoặc tổng quan ngắn gọn về cách phát hiện được

Remediation recommendations to resolve the finding // Khuyến nghị khắc phục để giải quyết phát hiện

Số lượng tài liệu báo cáo rất khác nhau tùy theo loại hình tham gia mà pentester tham gia. Báo cáo phát hiện thường có ba định dạng:

Kết quả quét lỗ hổng (danh sách đơn giản các lỗ hổng)

Tóm tắt kết quả (danh sách các phát hiện như đã nêu ở trên)

Báo cáo chính thức đầy đủ.

Như đã nêu trước đây, có nhiều cấp độ tài liệu khác nhau cho một báo cáo bằng văn bản cuối cùng. Dưới đây là cách mỗi loại báo cáo sẽ trông như thế nào trong thực tế:



Scan information :

Starttime

Finish time

Scan time (= finish - start)

profie

Server information:

Responsive

Server banner

Server OS

Server technologies ( nngu lap trinh)

Threat level

Alerts distribution

Total alerts found

(?) High

(?) Medium

(?) Low

(?) Informational

A findings summary is usually something like this: Finding: SQL Injection in ID Parameter of Cats Page Criticality: Critical Description: Placing a payload of 1' OR '1'='1 into the ID parameter of the website allowed the viewing of all cat names in the cat Table of the database. (Việc đặt tải trọng 1' HOẶC '1'='1 vào tham số ID của trang web cho phép xem tất cả tên mèo trong Bảng mèo của cơ sở dữ liệu.)

Furthermore, a UNION SELECT SQL statement allowed the attacker to view all usernames and passwords stored in the Accounts table. (Hơn nữa, câu lệnh SQL UNION SELECT cho phép kẻ tấn công xem tất cả tên người dùng và mật khẩu được lưu trữ trong bảng Tài khoản)

Remediation Recommendation: Utilize a Prepared SQL statement to prevent SQL injection attacks (Khuyến nghị khắc phục: Sử dụng câu lệnh SQL đã chuẩn bị để ngăn chặn các cuộc tấn công tiêm nhiễm SQL)

1 ví dụ :

` What would be the type of reporting that involves a full documentation of all findings within a formal document?

-> full formal report

What is the other thing that a pentester should provide in a report beyond: the finding name, the finding description, the finding criticality

-> Remediation Recommendation `
