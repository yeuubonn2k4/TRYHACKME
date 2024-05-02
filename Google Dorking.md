## Task 1 : Ye Ol' Search Engine

- Google được cho là ví dụ nổi tiếng nhất về “Công cụ tìm kiếm”, ý tôi là ai còn nhớ Ask Jeeves? rùng mình

- Bây giờ, việc giải thích cách thức hoạt động của các “Công cụ Tìm kiếm” này có thể khá là trịch thượng, nhưng còn rất nhiều điều đang diễn ra đằng sau hậu trường sau những gì chúng ta thấy. Quan trọng hơn, chúng ta có thể tận dụng lợi thế này để tìm ra tất cả những thứ mà một danh sách từ không thể làm được.  Nghiên cứu tổng thể - đặc biệt là trong bối cảnh An ninh mạng gói gọn hầu hết mọi việc bạn làm với tư cách là một pentester. MuirlandOracle  đã tạo ra một căn phòng tuyệt vời để tìm hiểu thái độ đối với cách nghiên cứu và chính xác những thông tin bạn có thể thu được từ nó.

- "Công cụ tìm kiếm" như Google là những công cụ lập chỉ mục khổng lồ - cụ thể là những công cụ lập chỉ mục nội dung trải rộng trên World Wide Web.

Những yếu tố cần thiết này khi lướt internet sử dụng “Trình thu thập thông tin” hoặc “Trình nhện” để tìm kiếm nội dung này trên World Wide Web, điều mà tôi sẽ thảo luận trong nhiệm vụ tiếp theo.

## Task 2 :

- Những trình thu thập thông tin này khám phá nội dung thông qua nhiều phương tiện khác nhau. Một là do khám phá thuần túy, trong đó một URL được trình thu thập thông tin truy cập và thông tin liên quan đến loại nội dung của trang web được trả về công cụ tìm kiếm. Trên thực tế, có rất nhiều thông tin được thu thập bởi các trình thu thập thông tin hiện đại – nhưng chúng ta sẽ thảo luận về cách sử dụng thông tin này sau. Một phương pháp khác mà trình thu thập dữ liệu sử dụng để khám phá nội dung là theo dõi bất kỳ và tất cả các URL được tìm thấy từ các trang web đã được thu thập dữ liệu trước đó. Giống như vi-rút ở chỗ nó sẽ muốn xâm nhập/lây lan đến mọi thứ có thể

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/0281edab-6db1-460d-8abd-ea22193fe8a6)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/b5fc148d-e63f-4702-a8b2-122eb23c2244)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/6b024abd-503b-4573-a0b3-fe9935be90f4)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/e7be4da4-0518-4480-a257-8bf5b4980ce3)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/ac4daf97-c133-45d1-9b33-1dca27cb4a20)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/b31160b4-9382-4e8d-a7e2-520546be0f16)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/1cce542a-19e0-45c1-884c-0e5524b6b205)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/1cae9e96-f46f-4e43-bd27-7641789f3041)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/8cd2ae70-5ae7-4b99-b0f9-8d884991746e)

## Task 3 :  Search Engine Optimisation

Để nêu bật một số ảnh hưởng đến cách tính điểm, các yếu tố như:

• Trang web của bạn phản hồi như thế nào với các loại trình duyệt khác nhau, tức là Google Chrome, Firefox và Internet Explorer - bao gồm cả Điện thoại di động!

• Việc thu thập thông tin trang web của bạn dễ dàng như thế nào (hoặc thậm chí nếu việc thu thập thông tin được cho phép ...nhưng chúng ta sẽ nói đến vấn đề này sau) thông qua việc sử dụng "Sơ đồ trang web"

• Trang web của bạn có loại từ khóa nào (ví dụ: Trong ví dụ của chúng tôi, nếu người dùng tìm kiếm truy vấn như “Màu sắc” thì sẽ không có tên miền nào được trả về - vì công cụ tìm kiếm chưa (chưa) thu thập dữ liệu tên miền có bất kỳ từ khóa nào cần thực hiện với “Sắc màu”

Ví dụ: hãy sử dụng Trình phân tích trang web của Google để kiểm tra xếp hạng của TryHackMe :

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/8d61220d-692c-4132-9902-c0f78c26f3a7)

## Task 4 : Beepboop - Robots.txt

Robots.txt

- Tương tự như "Sơ đồ trang web" mà chúng ta sẽ thảo luận sau, tệp này là thứ đầu tiên được "Trình thu thập thông tin" lập chỉ mục khi truy cập một trang web.

- Tệp này phải được cung cấp tại thư mục gốc - do chính máy chủ web chỉ định. Nhìn vào phần mở rộng tệp .txt này , khá an toàn khi cho rằng đó là tệp văn bản.

- Tệp văn bản xác định các quyền mà "Trình thu thập thông tin" có đối với trang web. Ví dụ: loại "Trình thu thập thông tin" nào được cho phép (Tức là bạn chỉ muốn "Trình thu thập thông tin" của Google lập chỉ mục trang web của bạn chứ không phải của MSN). Hơn nữa, Robots.txt có thể chỉ định những tệp và thư mục mà chúng tôi muốn hoặc không muốn được "Trình thu thập dữ liệu" lập chỉ mục.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/10a79085-d8ea-42ea-aaa9-a736b5cf6cca)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/eba0c73e-e90b-439b-bd62-f416c9313fac)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/ac453891-728c-47fb-88f2-e3ff8d470ab0)

Trong trường hợp này:

1. Bất kỳ "Trình thu thập thông tin" nào cũng có thể lập chỉ mục trang web

2. "Crawler" được phép lập chỉ mục toàn bộ nội dung của trang web

3. "Sơ đồ trang web" được đặt tại http://mywebsite.com/sitemap.xml

- Giả sử chúng tôi muốn ẩn các thư mục hoặc tệp khỏi "Trình thu thập thông tin"? Robots.txt hoạt động trên cơ sở "danh sách đen". Về cơ bản, trừ khi được yêu cầu khác , Trình thu thập thông tin sẽ lập chỉ mục bất cứ thứ gì nó có thể tìm thấy.

- Trong trường hợp này:

1. Bất kỳ "Trình thu thập thông tin" nào cũng có thể lập chỉ mục trang web

2. "Trình thu thập thông tin" có thể lập chỉ mục mọi nội dung khác không có trong "/super-secret-directory/".

Trình thu thập thông tin cũng biết sự khác biệt giữa các thư mục con, thư mục và tệp. Chẳng hạn như trong trường hợp "Không cho phép:" thứ hai ( "/not-a-secret/but-this-is/")

"Trình thu thập thông tin" sẽ lập chỉ mục tất cả nội dung trong " /not-a-secret/ ", nhưng sẽ không lập chỉ mục bất kỳ nội dung nào có trong thư mục con "/but-this-is/" .

3. "Sơ đồ trang web" được đặt tại  http://mywebsite.com/sitemap.xml

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/0af011a0-edf3-4e95-9c8c-2dc0e31266c7)

Làm thế nào về việc ngăn chặn các tập tin được lập chỉ mục? 

Mặc dù bạn có thể tạo các mục nhập thủ công cho mọi phần mở rộng tệp mà bạn không muốn bị lập chỉ mục, nhưng bạn sẽ phải cung cấp thư mục chứa phần mở rộng đó cũng như tên tệp đầy đủ. Hãy tưởng tượng nếu bạn có một trang web lớn! Thật là khó chịu...Đây là nơi chúng ta có thể sử dụng một chút biểu thức chính quy .

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/9c320c05-d6f0-480e-ae25-062b9868afe7)

Ví dụ: tại sao bạn muốn ẩn tệp .ini ? Chà, những tập tin như thế này chứa chi tiết cấu hình nhạy cảm. Bạn có thể nghĩ ra bất kỳ định dạng tệp nào khác có thể chứa thông tin nhạy cảm không?

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/c907f373-92a5-4cd6-b4e9-865acfc6eb82)

## Task 5 : Sitemaps

Có thể so sánh với bản đồ địa lý trong đời thực, “Sitemaps” chỉ có vậy - nhưng dành cho các trang web!

- “Sơ đồ trang web” là tài nguyên mang tính biểu thị hữu ích cho trình thu thập thông tin vì chúng chỉ định các lộ trình cần thiết để tìm nội dung trên miền. Hình minh họa dưới đây là một ví dụ điển hình về cấu trúc của một trang web và cách nó trông như thế nào trên "Sơ đồ trang web":

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/008cfacf-9bcc-4128-b153-ba3538ad9de0)

- Các hình chữ nhật màu xanh biểu thị đường dẫn đến nội dung lồng nhau, tương tự như thư mục I.e. “Sản phẩm” dành cho cửa hàng. Trong khi,
- , các hình chữ nhật bo tròn màu xanh lá cây tượng trưng cho một trang thực tế. Tuy nhiên, đây chỉ nhằm mục đích minh họa - “Sơ đồ trang web” không giống như thế này trong thế giới thực. Chúng trông giống như thế này hơn nhiều


![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/7a76044d-c2b1-4ff8-b75a-f79598a6c3d0)

- “Sơ đồ trang web” được định dạng XML. Tôi sẽ không giải thích cấu trúc của định dạng tệp này vì phòng XXE do falconfeast tạo ra thực hiện rất tốt việc này.

Sự hiện diện của "Sơ đồ trang web" có ảnh hưởng khá lớn đến việc "tối ưu hóa" và sự ưa thích của một trang web. Như chúng ta đã thảo luận trong tác vụ "Tối ưu hóa công cụ tìm kiếm", những bản đồ này giúp trình thu thập thông tin duyệt nội dung dễ dàng hơn nhiều!

` sitemap.xml `


![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/373a1847-e40c-44d6-a6a4-0aa690937ca8)

- Key cau 3 dua theo

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/85c397da-deb2-4da9-bf1d-26e91f647192)

## Task 6 : What is Google Dorking?


![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/f5132ddf-94eb-491c-bce3-cb869f4521c6)

Chúng tôi có thể sử dụng các thuật ngữ như “trang web” (chẳng hạn như bbc.co.uk) và một truy vấn (chẳng hạn như "gchq news") để tìm kiếm trang web được chỉ định cho từ khóa mà chúng tôi đã cung cấp nhằm lọc ra nội dung có thể khó tìm hơn nếu không thìVí dụ: bằng cách sử dụng “trang web” và "truy vấn" của "bbc" và "gchq", chúng tôi đã sửa đổi thứ tự Google trả về kết quả

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/786190fa-5a18-4920-964e-3577e6a4066d)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/c718535c-44bf-4d22-a631-f59fbcf2aac4)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/a5086a10-682f-4c7a-abf8-1b5177563d76)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/8f7409bf-b30a-46ea-86fd-4adceebbb754)


![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/bce91ece-d7cc-40f6-b49f-11654aed8a88)

