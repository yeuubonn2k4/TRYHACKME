The OSI Model An Overview
`

Lý Thuyết
Tang application
Cung cap ca tuy chon ket noi mang cho cac chuong trinh chay tren may tinh

Tang presention
Chuyen du lieu sang dinh dang chuan hoa cung nhu xu ly moi ma hoa, nen hoac cac bien doi khac voi du lieu

Tang session
Duy tri ket noi voi may tinh khac tren mang , phien tao ra la duy nhat cho giao tiep duoc de cap -> thuc hien dong thoi nhieu yeu cau den cac diem cuoi khac nhau ma khong lam xao tron du lieu ( vdu la mo 2 tab trong trinh duyet we cung 1 luc)

Tang transport
Chọn giao thức mà dữ liệu sẽ được truyền đi TCP, việc truyền tải dựa trên kết nối, có nghĩa là kết nối giữa các máy tính được thiết lập và duy trì trong suốt thời gian yêu cầu.Kết nối TCP cho phép hai máy tính duy trì liên lạc liên tục để đảm bảo dữ liệu được gửi ở tốc độ chấp nhận được và mọi dữ liệu bị mất sẽ được gửi lại UDP về cơ bản các gói dữ liệu sẽ được ném vào máy tính nhận - nếu nó không theo kịp thì đó là vấn đề (đây là lý do tại sao việc truyền video qua thứ gì đó như Skype có thể bị tạo pixel nếu kết nối kém). Điều này có nghĩa là TCP thường được chọn cho các tình huống mà độ chính xác được ưu tiên hơn tốc độ (ví dụ: truyền tệp hoặc tải trang web) và UDP sẽ được sử dụng trong các tình huống mà tốc độ quan trọng hơn (ví dụ: truyền phát video). Với một giao thức được chọn, lớp vận chuyển sẽ chia quá trình truyền thành các phần có kích thước nhỏ (trên TCP, chúng được gọi là các phân đoạn, trên UDP, chúng được gọi là datagram), giúp truyền tin nhắn thành công dễ dàng hơn

Tang network
Xác định đích đến của yêu cầu của bạn

Tang Datalink
Đánh địa chỉ vật lý của đường truyền Trình bày dữ liệu ở định dạng phù hợp để truyền tải. kiểm tra thông tin nhận được để đảm bảo rằng nó không bị hỏng trong quá trình truyền

Tang Physical
Nam ngay duoi phan cung may tinh Chuyển đổi dữ liệu nhị phân của quá trình truyền thành tín hiệu và truyền chúng qua mạng, cũng như nhận tín hiệu đến và chuyển đổi chúng trở lại thành dữ liệu nhị phân. `

`

TASK
Which layer would choose to send data over TCP or UDP?

-> 4

Which layer checks received information to make sure that it hasn't been corrupted?

-> 2

In which layer would data be formatted in preparation for transmission?

-> 2

Which layer transmits and receives data?

-> 1

Which layer encrypts, compresses, or otherwise transforms the initial data to give it a standardised format?

-> 6

Which layer tracks communications between the host and receiving computers?

-> 5

Which layer accepts communication requests from applications?

-> 7

Which layer handles logical addressing?

-> 3

When sending data over TCP, what would you call the "bite-sized" pieces of data?

-> segments

[Research] Which layer would the FTP protocol communicate with?

-> 7

Which transport layer protocol would be best suited to transmit a live video?

-> UDP

`

Encapsulation
How would you refer to data at layer 2 of the encapsulation process (with the OSI model)?

-> frames

How would you refer to data at layer 4 of the encapsulation process (with the OSI model), if the UDP protocol has been selected?

-> datagram

What process would a computer perform on a received message?

-> de-encapsulation

Which is the only layer of the OSI model to add a trailer during encapsulation?

-> data link

Does encapsulation provide an extra layer of security (Aye/Nay)?

-> Aye

THE TCP/IP MODEL
Lý thuyết  TCP 	là giao thức dựa trên kết nối ( trước khi gửi bất kì dữ liệu nào qua TCP, trước tiên bạn phải tạo kết nối ổn địn gữa hai máy tính) -> BẮT TAY BA BƯỚC																							 Quy tắc bắt tay 3 bước																								 B1	máy tính của bạn sẽ gửi một yêu cầu đặc biệt đến máy chủ từ xa cho biết rằng nó muốn khởi tạo kết nối (SYN : đồng bộ hó, tạo liên hệ đầu tiên khi bắt đầu quá trình kết nối)																							 B2	Sau đó, máy chủ sẽ phản hồi bằng gói chứa bit SYN/ACK																							 B3	 máy tính của bạn sẽ gửi một gói chứa bit ACK, xác nhận rằng kết nối đã được thiết lập thành công.																							 -> Khi quá trình bắt tay ba chiều được hoàn tất thành công, dữ liệu có thể được truyền đi một cách đáng tin cậy giữa hai máy tính. Bất kỳ dữ liệu nào bị mất hoặc bị hỏng trong quá trình truyền sẽ được gửi lại, do đó dẫn đến kết nối dường như không bị mất.																								

Which model was introduced first, OSI or TCP/IP?

-> TCP/IP

Which layer of the TCP/IP model covers the functionality of the Transport layer of the OSI model (Full Name)?

-> Transport

Which layer of the TCP/IP model covers the functionality of the Session layer of the OSI model (Full Name)?

-> Application

The Network Interface layer of the TCP/IP model covers the functionality of two layers in the OSI model. These layers are Data Link, and?.. (Full Name)?

-> physical

Which layer of the TCP/IP model handles the functionality of the OSI network layer?

-> internet

What kind of protocol is TCP?

-> connection-based

What is SYN short for?

-> synchronise

What is the second step of the three way handshake?

-> SYN/ACK

What is the short name for the "Acknowledgement" segment in the three-way handshake?

-> ACK

ping
`

Lý thuyết
ping khi nào? chúng ta muốn kiểm tra xem có thể kết nối với tài nguyên từ xa hay không.nhưng nó cũng có thể dành cho một máy tính trong mạng gia đình của bạn nếu bạn muốn kiểm tra xem nó đã được cấu hình đúng chưa hoạt động bằng giao thức ICMP hoạt động trên lớp Mạng của Mô hình OSI và do đó là lớp Internet của mô hình TCP/IP. Lưu ý rằng lệnh ping thực sự trả về địa chỉ IP cho máy chủ Google mà nó kết nối tới chứ không phải URL được yêu cầu. các tuỳ chọn của ping "-I : Chỉ định giao diện mạng cụ thể để sử dụng khi gửi gói tin ping. " vd ping -i eth0 192.168.1.1 -4: yêu cầu ping sử dụng giao thức IPv4 để gửi các gói tin ICMP. -> -6 -v : bật chế độ verbose (có thể hiểu là "chi tiết") khi thực hiện ping -c : Chỉ định số lượng gói tin ping sẽ được gửi trước khi quá trình ping dừng lại. -s : Chỉ định kích thước gói tin ping (trong byte). -t : Chỉ định số thời gian sống (TTL - Time to Live) của gói tin ping. -W : Chỉ định thời gian chờ tối đa (trong mili-giây) cho mỗi gói tin ping. -q: Chế độ "Quiet", làm cho ping chỉ hiển thị kết quả cuối cùng mà không hiển thị thông tin chi tiết về mỗi gói tin. -n: Hiển thị địa chỉ IP thay vì cố gắng giải quyết tên miền. ` What command would you use to ping the bbc.co.uk website?

-> ping bbc.co.uk

What is the IPv4 address?

-> 217.160.0.152

What switch lets you change the interval of sent ping requests?

-> -i

What switch would allow you to restrict requests to IPv4?

-> -4

What switch would give you a more verbose output?

-> -v

Traceroute
`

Lý thuyết
traceroute kiểm tra tuyến đường đi của gói dữ liệu (xem gặp sự cố ở bước nào) nó cho phép bạn xem từng kết nối tracert + địa chỉ IP đích nó hiện thời gian mỗi bước, địa chỉ IP

hoạt động bằng cách sử dụng giao thức ICMP mà ping sử dụng và giao thức Unix tương đương hoạt động trên UDP ->> Có thể thay đổi được bằng các công tắc trong cả hai trường hợp
What switch would you use to specify an interface when using Traceroute?

-> -i

What switch would you use if you wanted to use TCP SYN requests when tracing the route?

-> -t

[Lateral Thinking] Which layer of the TCP/IP model will traceroute run on by default (Windows)?

-> internet

WHOIS
`

Lý thuyết
domains dịch địa chỉ tên miền thành IP tự động ( nó sẽ yêu cầu 1 máy chủ đặc biệt dịch cho chúng ta) ví dụ : khi chúng ta muốn vào 1 trang web, chúng ta cần gõ tên miền là vào được chứ không cần nhớ địa chỉ Ip vì khi gõ tên miền , domains nó tự động dịch về địa chỉ Ip và mt chúng ta sẽ truy cập tớii đó

Domain Registrars bên cho thuê miền ( Nhà đăng kí tên miền) trong 1 khoảng thời gian nhất định

WHOIS cho phép bạn truy vấn tên miền được đăng kí bởi ai _> có thể tìm ra thông tin của họ https://who.is/whois/microsoft.com

Tải whois sudo apt-get install whois xoá sudo apt-get remove whois cập nhật sudo apt-get update

cú pháp WHOIS whois + tên miền ` What is the registrant postal code for facebook.com?

-> 94025

When was the facebook.com domain first registered (Format: DD/MM/YYYY)?

-> 29/03/1997

Perform a whois search on microsoft.com

Which city is the registrant based in?

-> Redmond

DIG
`

Lý thuyết
DNS Giả sử địa chỉ chưa được tìm thấy thì máy tính của bạn sẽ gửi yêu cầu đến máy chủ DNS đệ quy. Những điều này sẽ tự động được bộ định tuyến trên mạng của bạn biết đến.nếu mà k tìm được địa chỉ IP trong bộ nhớ đệm -> RESOLVER SERVER (VNPT, Viettel,..) nếu k có -> ROOT sẻver ( nơi có 1 địa chỉ ip duy nhất, nó sẽ điều hướng cho TLD ( lưu trữ thông tin cho các tên miền như .com,.net,.org,..) sau đó chuyển hướng nơi cuối cùng là Name Server (nơi biết mọi thứ từ nguồn) sau đó chuyển lại réolver server ( sau đó nó sẽ lưu lại vào bộ nhớ đệm để lần sau tìm kiếm nó sẽ thấy -> cải thiện tốc độ trang web rất nhiều) sau đó mới chuyển thông tin về mt của chúng ta dig cho phép chúng tôi truy vấn thủ công các máy chủ DNS đệ quy mà chúng tôi lựa chọn để biết thông tin về tên miền cú pháp dig < domain> @ Dig cung cấp cho chúng ta là TTL (Time To Live) của bản ghi DNS được truy vấn khi máy tính của bạn truy vấn một tên miền, nó sẽ lưu kết quả vào bộ đệm cục bộ.TTL của bản ghi sẽ cho máy tính của bạn biết khi nào nên dừng coi bản ghi là hợp lệ -- tức là khi nào máy tính nên yêu cầu lại dữ liệu, thay vì dựa vào bản sao được lưu trong bộ nhớ đệm.TTL (trong ngữ cảnh bộ nhớ đệm DNS) được tính bằng giây ` What is DNS short for?

-> Domain Name System

What is the first type of DNS server your computer would query when you search for a domain?

-> recursive

What type of DNS server contains records specific to domain extensions (i.e. .com, .co.uk*, etc)*? Use the long version of the name.

-> Top-Level Domains

Where is the very first place your computer would look to find the IP address of a domain?

-> Hosts File

[Research] Google runs two public DNS servers. One of them can be queried with the IP 8.8.8.8, what is the IP address of the other one?

-> 8.8.4.4

If a DNS query has a TTL of 24 hours, what number would the dig query show?

-> 86400

[OSINT] What is the name of the golf course that is near the registrant address for microsoft.com?

-> Bellevue Golf Course

What is the registered Tech Email for microsoft.com?

-> msnhst@microsoft.com (linux : whois microsoft.com | grep -i tech)
