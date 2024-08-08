> Tim hieu ve quan ly phien. Sau khi xac thuc, ban se duoc cung cap 1 session, sesion nay duoc ung dung web su dung de Save trang thai cua ban, theo doi cac hanh dong cua ban va quyet dinh xem ban co duoc phep lam nhung gi ban dang muon lam khong

-> Quan ly session nham Dam bao rang cac buoc nay duoc thuc hien chinh xac, neu khong ke tan cong co the xam pham phien cua ban va chiem doat no 1 cach hieu qua .

`
**Mục tiêu học tập**

- Hiểu Quản lý phiên là gì

- Hiểu được sự khác biệt giữa xác thực và ủy quyền và cách chúng đóng vai trò trong quản lý phiên

- Tìm hiểu về hai phương pháp quản lý phiên chính

- Tìm hiểu về vòng đời quản lý phiên

- Tìm hiểu cách khai thác thực tế các triển khai quản lý phiên dễ bị tấn công

## 2. Quan ly phien la gi?

- Vong doi qua Session Management

![image](https://github.com/user-attachments/assets/bf981dc4-19a1-4ae6-b31e-1525ee846855)

- Tao phien

* Sau khi cung cap ten nguoi dung va mat khau, ban se nhan duoc gia tri phien sau do duoc gui voi moi yeu cau moi. Cach cac gia tri phien nay duoc tao, su dung va luu tru la rat quan trong trong viec bao mat viec tao phien.

- Theo doi phien

Vì giao thức HTTP không có trạng thái, nên có thể xảy ra trường hợp người dùng ứng dụng web đột nhiên ngừng sử dụng

Ví dụ, bạn có thể đóng tab hoặc toàn bộ trình duyệt của mình. Vì giao thức không có trạng thái, nên ứng dụng web không có phương pháp nào để biết rằng hành động này đã xảy ra.

Đây là lúc hết hạn phiên phát huy tác dụng. Bản thân giá trị phiên của bạn phải có thời gian tồn tại được gắn vào. Nếu thời gian tồn tại hết hạn và bạn gửi giá trị phiên cũ cho ứng dụng web, thì giá trị đó phải bị từ chối vì phiên phải đã hết hạn. Thay vào đó, bạn phải được chuyển hướng đến trang đăng nhập để xác thực lại và bắt đầu lại toàn bộ vòng đời quản lý phiên!

***Cai nay giong nhu de qa luu hoac thoat ra thi ban se bi kick ra va yeu cau Dang nhap tro lai***

- Ket thuc phien

*Tuy nhiên, trong một số trường hợp, người dùng có thể buộc phải thực hiện hành động đăng xuất. Trong trường hợp này xảy ra, ứng dụng web sẽ chấm dứt phiên của người dùng. Mặc dù điều này tương tự như việc hết hạn phiên, nhưng nó độc đáo ở chỗ ngay cả khi thời gian tồn tại của phiên vẫn còn hiệu lực, thì bản thân phiên đó cũng phải bị chấm dứt. Các vấn đề trong quá trình chấm dứt này có thể cho phép tác nhân đe dọa có được quyền truy cập liên tục vào một tài khoản.

![image](https://github.com/user-attachments/assets/59859043-3af5-48b5-85a3-abfcd9efae6c)

## 3. Authentication vs Authorisation

Để hiểu các lỗ hổng phổ biến trong quản lý phiên, trước tiên chúng ta cần xem xét xác thực và ủy quyền. Mặc dù chúng nghe có vẻ giống nhau và thường bị nhầm lẫn, nhưng mỗi loại đều đóng vai trò quan trọng và riêng biệt trong quản lý phiên. Để giải thích rõ hơn về sự khác biệt, chúng ta hãy xem xét mô hình IAAA :

![image](https://github.com/user-attachments/assets/255375f5-0a91-49c4-8038-f436af1bd45e)

- Identification

Nhan dang la qua trinh xac minh nguoi dung la ai.

***Quá trình này bắt đầu bằng việc người dùng tự nhận là một danh tính cụ thể. Trong hầu hết các ứng dụng web, quá trình này được thực hiện bằng cách gửi tên người dùng của bạn. Bạn đang tự nhận mình là người được liên kết với tên người dùng cụ thể. Một số ứng dụng sử dụng tên người dùng được tạo riêng, trong khi những ứng dụng khác sẽ lấy địa chỉ email của bạn làm tên người dùng.***

*Cai nay giong nhu kieu qua trinh Dang nhap fb vay*

- Authentication

* la qua trinh dam bao rang nguoi dung la nguoi ma ho noi ho la.

***Trong khi trong nhận dạng, bạn cung cấp tên người dùng, đối với xác thực, bạn cung cấp bằng chứng rằng bạn là người mà bạn nói bạn là. Ví dụ, bạn có thể cung cấp mật khẩu được liên kết với tên người dùng đã khai báo. Ứng dụng web có thể xác nhận thông tin này nếu nó hợp lệ; đây là thời điểm mà việc tạo phiên sẽ bắt đầu.***

*Giong nhu kieu xac nhan tai khoan Zalo*

- Authorisation : la qua trinh dam bao rang nguoi dung cu the co cac quyen can thiet de thuc hien hanh dong duoc yeu cau

*Ví dụ, trong khi tất cả người dùng có thể xem dữ liệu, chỉ một số ít người được chọn mới có thể sửa đổi dữ liệu đó. Trong vòng đời quản lý phiên, theo dõi phiên đóng vai trò quan trọng trong ủy quyền.* 

- Accountability : qua trinh tao ra 1 ban ghi ve cac hanh dong duoc thuc hien boi nguoin dung.  Chúng ta nên theo dõi phiên của người dùng và ghi lại tất cả các hành động được thực hiện bằng phiên cụ thể. Thông tin này đóng vai trò quan trọng trong trường hợp xảy ra sự cố bảo mật để ghép nối những gì đã xảy ra.

- IAAA and Session Management :
- 
Bây giờ bạn đã hiểu sự khác biệt giữa xác thực và ủy quyền, hãy quay lại vấn đề quản lý phiên. Xác thực đóng vai trò trong cách tạo phiên. Ủy quyền trở nên quan trọng để xác minh rằng người dùng được liên kết với một phiên cụ thể có quyền thực hiện hành động mà họ yêu cầu. Trách nhiệm giải trình rất quan trọng để chúng tôi ghép nối những gì thực sự xảy ra trong một sự cố, nghĩa là điều quan trọng là các yêu cầu được ghi lại và phiên được liên kết với mỗi yêu cầu cũng được ghi lại.

![image](https://github.com/user-attachments/assets/993b1838-c089-40e4-9529-4f20eda44ad8)

## 4. Cookies vs Tokens

Hai cách tiếp cận chính là cookie và mã thông báo, mỗi cách đều có lợi ích và hạn chế riêng.

### Cookie-Based Session Management : Quan ly phien dua tren cookie

Quản lý phiên dựa trên cookie thường được gọi là cách quản lý phiên theo kiểu cũ. Khi ứng dụng web muốn bắt đầu theo dõi, trong phản hồi, giá trị tiêu đề Set-Cookie sẽ được gửi. Trình duyệt của bạn sẽ diễn giải tiêu đề này để lưu trữ giá trị cookie mới. Hãy cùng xem xét tiêu đề Set-Cookie như vậy:

**Set-Cookie: session=12345;**

Trình duyệt của bạn sẽ tạo một mục nhập cookie cho một cookie được đặt tên sessionvới giá trị 12345sẽ hợp lệ cho miền mà cookie được nhận. Một số thuộc tính cũng có thể được thêm vào tiêu đề này. Nếu bạn muốn tìm hiểu thêm về tất cả các thuộc tính này, vui lòng tham khảo tại đây , nhưng một số thuộc tính đáng chú ý là:

**Bảo mật** - Chỉ ra cho trình duyệt rằng cookie chỉ có thể được truyền qua các kênh HTTPS đã xác minh. Nếu có lỗi chứng chỉ hoặc sử dụng HTTP , giá trị cookie sẽ không được truyền.

**HTTPOnly** - Chỉ ra cho trình duyệt biết rằng giá trị cookie có thể không được JavaScript phía máy khách đọc.

**Hết hạn** - Chỉ ra cho trình duyệt thời điểm giá trị cookie không còn hiệu lực và cần được xóa.

**SameSite** - Chỉ ra cho trình duyệt liệu cookie có thể được truyền trong các yêu cầu liên trang web hay không để giúp bảo vệ chống lại các cuộc tấn công CSRF 

Một điều quan trọng cần nhớ với xác thực dựa trên cookie là trình duyệt sẽ tự quyết định khi nào một giá trị cookie nhất định sẽ được gửi cùng với yêu cầu. Sau khi xem xét tên miền và các thuộc tính của cookie, trình duyệt sẽ đưa ra quyết định này và cookie được tự động đính kèm mà không cần bất kỳ mã JavaScript nào ở phía máy khách.

### Token-Based Session Management : Quản lý phiên dựa trên mã thông báo

Quản lý phiên dựa trên mã thông báo là một khái niệm tương đối mới. Thay vì sử dụng các tính năng quản lý cookie tự động của trình duyệt, nó dựa vào mã phía máy khách cho quy trình. Sau khi xác thực, ứng dụng web cung cấp một mã thông báo trong nội dung yêu cầu. Sử dụng mã JavaScript phía máy khách, mã thông báo này sau đó được lưu trữ trong LocalStorage của trình duyệt.

Khi một yêu cầu mới được thực hiện, mã JavaScript phải tải mã thông báo từ bộ lưu trữ và đính kèm nó dưới dạng tiêu đề. Một trong những loại mã thông báo phổ biến nhất là JSON Web Tokens (JWT), được truyền qua Authorization: Bearertiêu đề. Tuy nhiên, vì chúng tôi không sử dụng các tính năng quản lý cookie tích hợp của trình duyệt, nên đây là một chút miền Tây hoang dã nơi mọi thứ đều có thể xảy ra. Mặc dù có các tiêu chuẩn, nhưng không có gì thực sự buộc bất cứ điều gì phải tuân theo các tiêu chuẩn này.

Lợi ích và Nhược điểm

#### Ưu điểm và nhược điểm của từng phương pháp này đều có liên quan trực tiếp với nhau, chúng ta hãy cùng xem xét:

- Quản lý phiên Cookie (*)

Quản lý phiên dựa trên mã thông báo (-)

- Cookie được trình duyệt tự động gửi với mỗi yêu cầu (*)

Mã thông báo phải được gửi dưới dạng tiêu đề với mỗi yêu cầu bằng JavaScript phía máy khách (-)

- Thuộc tính cookie có thể được sử dụng để tăng cường khả năng bảo vệ cookie của trình duyệt (*)

Mã thông báo không có biện pháp bảo vệ an ninh tự động được thực thi và do đó, cần được bảo vệ chống lại việc tiết lộ (-)

- Cookie có thể dễ bị tấn công từ phía máy khách thông thường như CSRF , khi đó trình duyệt bị lừa đưa ra yêu cầu thay mặt cho người dùng. (*)

Vì mã thông báo không được tự động thêm vào bất kỳ yêu cầu nào và không thể được đọc từ LocalStorage bởi các miền khác, nên các cuộc tấn công phía máy khách thông thường như CSRF sẽ bị chặn. (-)

- Vì cookie bị khóa trong một miền cụ thể nên có thể khó sử dụng chúng một cách an toàn trong các ứng dụng web phi tập trung. (*)

Mã thông báo hoạt động tốt trong các ứng dụng web phi tập trung vì chúng được quản lý thông qua JavaScript và thường có thể chứa tất cả thông tin cần thiết để xác minh mã thông báo.    (-)

#### Tham khao https://quantrimang.com/hoc/cac-truong-header-trong-http-156082

![image](https://github.com/user-attachments/assets/0f33f881-2184-48f4-b238-ea10f314491f)

## 5. Securing the Session Lifecycle

Cuối cùng đã đến lúc tìm hiểu về bảo mật quản lý phiên. Quay trở lại vòng đời quản lý phiên của chúng ta, hãy cùng xem xét những gì có thể xảy ra sai sót ở từng giai đoạn.

- Tạo phiên

Việc tạo phiên là nơi dễ xảy ra nhiều lỗ hổng nhất. Chúng ta hãy cùng tìm hiểu một số lỗ hổng phổ biến.

### Weak Session Values

Ít phổ biến hơn khi thấy các giá trị phiên yếu trong thời hiện đại vì các khuôn khổ được sử dụng liên tục. Tuy nhiên, với sự gia tăng của LLM và các giải pháp trợ lý mã AI khác, bạn sẽ ngạc nhiên về tần suất các lỗ hổng cũ này đang quay trở lại.

Nếu một cơ chế tạo phiên tùy chỉnh đã được triển khai, có khả năng cao là các giá trị phiên có thể đoán được. Một ví dụ điển hình về điều này là cơ chế chỉ mã hóa base64 tên người dùng thành giá trị phiên. Nếu một tác nhân đe dọa có thể đảo ngược quá trình tạo phiên, chúng có thể tạo hoặc đoán các giá trị phiên để chiếm đoạt tài khoản của người dùng hợp pháp.

### Controllable Session Values

Trong một số mã thông báo, chẳng hạn như JWT, tất cả thông tin có liên quan để tạo và xác minh tính hợp lệ của JWT đều được cung cấp. Nếu các biện pháp bảo mật không được thực thi, chẳng hạn như xác minh chữ ký của mã thông báo hoặc đảm bảo rằng chữ ký đó được tạo ra một cách an toàn, thì tác nhân đe dọa sẽ có thể tạo mã thông báo của riêng chúng. Các loại tấn công này sẽ được thảo luận chi tiết hơn trong một phòng sau.

### Session Fixation

Bạn còn nhớ ứng dụng web đã cung cấp cho bạn một phiên trước khi xác thực không? Các ứng dụng web này có thể dễ bị tấn công bởi một thứ gọi là cố định phiên. Nếu giá trị phiên của bạn không được xoay vòng đầy đủ sau khi bạn xác thực, một tác nhân đe dọa ở vị trí phù hợp có thể ghi lại giá trị đó khi bạn vẫn chưa xác thực và chờ bạn xác thực để có quyền truy cập vào phiên của bạn.

### Insecure Session Transmission

Trong môi trường hiện đại, máy chủ xác thực và máy chủ ứng dụng thường tách biệt. Hãy nghĩ về những thứ như giải pháp Đăng nhập một lần (SSO). Một ứng dụng được sử dụng để xác thực cho một số ứng dụng web khác. Để quy trình này hoạt động, tài liệu phiên của bạn phải được chuyển từ máy chủ xác thực sang máy chủ ứng dụng thông qua trình duyệt của bạn. Tuy nhiên, trong quá trình truyền này, một số vấn đề nhất định có thể xảy ra khiến thông tin phiên của bạn bị tiết lộ cho tác nhân đe dọa. Phổ biến nhất là chuyển hướng không an toàn, trong đó tác nhân đe dọa có thể kiểm soát URL mà bạn sẽ được chuyển hướng đến sau khi xác thực. Điều này có thể cho phép tác nhân đe dọa chiếm đoạt phiên của bạn. Không chỉ với các triển khai tùy chỉnh, giải pháp SSO của Oracle có một lỗi lớn cho phép điều này xảy ra .

- Theo dõi phiên

Theo dõi phiên là thủ phạm lớn thứ hai gây ra lỗ hổng. Chúng ta hãy cùng xem xét.

### Authorisation Bypass

Bỏ qua ủy quyền xảy ra khi không có đủ các kiểm tra được thực hiện để xác định xem người dùng có được phép thực hiện hành động mà họ yêu cầu hay không. Về bản chất, điều này không theo dõi đúng phiên của người dùng và các quyền liên quan của người dùng. Cũng đáng để nói về hai loại bỏ qua ủy quyền:

Bỏ qua theo chiều dọc - Bạn có thể thực hiện một hành động dành riêng cho người dùng có đặc quyền hơn

Bỏ qua theo chiều ngang - Bạn có thể thực hiện một hành động mà bạn được phép thực hiện, nhưng trên một tập dữ liệu mà bạn không được phép thực hiện hành động đó

Trong hầu hết các ứng dụng, bỏ qua theo chiều dọc dễ bảo vệ vì các trình trang trí hàm và cấu hình kiểm soát truy cập dựa trên đường dẫn được sử dụng. Tuy nhiên, với bỏ qua theo chiều ngang, người dùng đang thực hiện một hành động mà họ nên được phép thực hiện. Vấn đề là họ đang thực hiện hành động đó trên dữ liệu của người khác. Để khắc phục điều này, cần có mã thực tế để xác minh người dùng là ai (trích xuất từ ​​phiên của họ), dữ liệu nào họ đang yêu cầu và liệu họ có được phép yêu cầu hoặc sửa đổi tập dữ liệu hay không.

### Insufficient Logging

Ghi nhật ký không đủ

Một vấn đề chính trong các sự cố là không có đủ thông tin để ghép lại thành một cuộc tấn công. Trong khi nhiều hoạt động ghi nhật ký sẽ diễn ra ở cấp độ cơ sở hạ tầng, hoạt động ghi nhật ký ứng dụng có thể rất quan trọng để hiểu được điều gì đã xảy ra sai. Trong trường hợp các hành động do một phiên cụ thể thực hiện và khả năng truy vết phiên đó đến người dùng không tồn tại, điều này có thể để lại những khoảng trống trong quá trình điều tra mà không thể lấp đầy. Cũng đáng để đảm bảo rằng các bản ghi bao gồm cả các hành động được chấp nhận và bị từ chối. Trong trường hợp xảy ra một cuộc tấn công chiếm đoạt phiên, các hành động sẽ có vẻ hợp lệ. Do đó, chỉ ghi nhật ký các hành động bị từ chối là không đủ để vẽ nên bức tranh.


Mã thông báo hoạt động tốt trong các ứng dụng web phi tập trung vì chúng được quản lý thông qua JavaScript và thường có thể chứa tất cả thông tin cần thiết để xác minh mã thông báo.

- Session Expiry

Phiên hết hạn chỉ có một lỗ hổng duy nhất, đó là khi thời gian hết hạn cho các phiên quá dài. Một phiên nên được xem như một tấm vé xem phim. Mỗi đêm, cùng một bộ phim được chiếu, nhưng chúng tôi không muốn ai đó có thể sử dụng cùng một tấm vé để xem lại bộ phim. Tương tự đối với các phiên, chúng tôi cần đảm bảo rằng thời gian hết hạn phiên của chúng tôi có tính đến trường hợp sử dụng cụ thể của ứng dụng. Ứng dụng ngân hàng nên có thời gian tồn tại của phiên ngắn hơn so với ứng dụng thư web của bạn.

Hơn nữa, trong trường hợp các phiên dài hạn, chẳng hạn như các phiên cho máy khách webmail, thì chính phiên đó phải chứng thực cho vị trí mà nó được sử dụng. Nếu vị trí này thay đổi (có thể là dấu hiệu của việc chiếm đoạt phiên), thì phiên đó phải bị chấm dứt.

- Session Termination

Đối với việc chấm dứt phiên, vấn đề chính là khi các phiên không được chấm dứt đúng cách ở phía máy chủ khi hành động đăng xuất được thực hiện. Giả sử một tác nhân đe dọa chiếm đoạt phiên của người dùng. Trong trường hợp đó, ngay cả khi người dùng nhận thức được vấn đề, nếu không có khả năng vô hiệu hóa phiên ở phía máy chủ, thì người dùng không có phương pháp nào để xóa quyền truy cập của tác nhân đe dọa. Tuy nhiên, đây có thể là một vấn đề khá lớn đối với các mã thông báo mà thời hạn sử dụng của mã thông báo được nhúng trong chính mã thông báo đó. Trong những trường hợp này, mã thông báo có thể được thêm vào danh sách chặn để xác minh. Một số ứng dụng cũng thực hiện điều này xa hơn khi tất cả các phiên của người dùng có thể được xem và chấm dứt. Hơn nữa, sau khi đặt lại mật khẩu thành công, chúng tôi cũng khuyến nghị chấm dứt tất cả các phiên để cho phép người dùng lấy lại toàn quyền kiểm soát tài khoản của họ.

![image](https://github.com/user-attachments/assets/b6ae16ef-477c-4892-8c59-61b1c73004ab)

## 6. Exploiting Insecure Session Management

### Enumeration

Để khai thác hiệu quả vòng đời quản lý phiên dễ bị tấn công, trước tiên chúng ta cần tự lập bản đồ vòng đời và ghi lại các ghi chú chi tiết. Khi đã hiểu được vòng đời dự định, chúng ta có thể bắt đầu tìm kiếm điểm yếu. Chúng ta sẽ sử dụng các công cụ trình duyệt tích hợp cho phần trình diễn này. Tuy nhiên, bạn cũng có thể làm theo các công cụ kiểm tra ứng dụng web nâng cao hơn, chẳng hạn như Burp. Trước tiên, hãy điều hướng đến ứng dụng của chúng ta tại http://MACHINE_IP và chúng ta sẽ thấy trang sau:

![image](https://github.com/user-attachments/assets/bf6c8660-511b-4a8a-8395-c39b0aa400c0)

![image](https://github.com/user-attachments/assets/bc6e25c0-efba-4f03-973f-12253d2a8ed7)

Đầu tiên, chúng ta nhận thấy rằng chúng ta không được cung cấp bất kỳ cookie hoặc mã thông báo nào khi lần đầu tiên truy cập trang. Điều này cho chúng ta biết rằng các phiên chưa xác thực rất có thể không được theo dõi. Nếu chúng ta nhấp vào nút Đăng ký, chúng ta thấy có hai lần đăng ký chính:

Sinh viên - Bất kỳ ai cũng có thể sử dụng để tạo hồ sơ

Giảng viên - Yêu cầu mã xác minh cho quá trình đăng ký

Điều này cho chúng ta thấy rằng ngay cả khi không có bất kỳ kỹ thuật brute-force nào, chúng ta vẫn có thể bắt đầu vòng đời quản lý phiên bằng cách tạo một tài khoản sinh viên. Hãy tạo một tài khoản sinh viên và xem điều gì xảy ra:

au khi tạo tài khoản người dùng, chúng ta nhận được lời nhắc rằng tài khoản đã được tạo và chúng ta được điều hướng trở lại trang đăng nhập. Hãy thực hiện đăng nhập với tư cách là người dùng của chúng ta và theo dõi lưu lượng mạng:

![image](https://github.com/user-attachments/assets/10dd0dd9-9913-4d79-89bc-8f9c735883da)

![image](https://github.com/user-attachments/assets/5760aea1-28e8-48d3-a1f6-a662abcefb35)

![image](https://github.com/user-attachments/assets/1cc346fa-5819-4c09-b431-8a1ca70aef71)

![image](https://github.com/user-attachments/assets/e1c0ca1f-753a-4694-940b-8faf40bd2c9e)

uy nhiên, có lẽ chúng ta nên kiểm tra xem phiên có bị chấm dứt ở phía máy chủ không. Bạn có thể xác thực lại với ứng dụng và thay thế cookie mới bằng giá trị cookie cũ. Nhưng có vẻ như việc chấm dứt phiên đang hoạt động ở một mức độ nào đó vì bạn nhận được Lỗi máy chủ nội bộ 500 khi làm mới trang. Điều này cho chúng ta biết rằng có điều gì đó không ổn ở đây, vì một phiên không hợp lệ không nên dẫn đến lỗi máy chủ nội bộ. Hãy cùng điều tra.

Chúng ta hãy xem lại một số tuyên bố trước đây của chúng tôi ở đây. Nếu chúng ta điều hướng đến Lưu trữ cục bộ, chúng ta nhận thấy khá nhiều dữ liệu đang được lưu trữ:

![image](https://github.com/user-attachments/assets/ebfa5128-984a-47d8-8c57-0987052988cd)

Mặc dù hiện tại chúng ta có thể truy cập vào nhiều tab hơn, nhưng có vẻ như chúng ta không thể truy cập vào nhiều thông tin hơn vì chúng ta không thể xem bất kỳ học sinh hoặc bài kiểm tra nào. Hãy tiến xa hơn bằng cách cập nhật vai trò của chúng ta trong giá trị người dùng từ 2 lên 3. Thật đáng buồn, điều này vẫn mang lại cho chúng ta cùng một kết quả. Tuy nhiên, có nhiều giá trị hơn để sử dụng ở đây, chẳng hạn như id và tên người dùng của chúng ta. Chúng ta sẽ phải quay lại vấn đề này. Tuy nhiên, thông tin mới này cho chúng ta biết rằng các phiên có thể được quản lý không chỉ thông qua cookie mà thông qua thông tin mã thông báo.

Bây giờ, chúng ta đã lập bản đồ vòng đời quản lý phiên. Chúng ta hãy cùng xem xét:

Giai đoạn vòng đời

Quan sát

**Tạo phiên**

Sự kết hợp giữa quản lý phiên dựa trên cookie và mã thông báo đang được sử dụng

**Tạo phiên**

Một giá trị phiên mới được cung cấp cho mỗi lần đăng nhập

**Tạo phiên**

Bản thân giá trị phiên dường như đủ ngẫu nhiên

**Theo dõi phiên**

Các hành động chưa xác thực không được theo dõi thông qua phiên

**Theo dõi phiên**

Cookie được gửi trong mỗi yêu cầu theo dõi

**Theo dõi phiên**

Có thể thực hiện một số yêu cầu mà không cần cookie

**Theo dõi phiên**

Các giá trị mã thông báo ban đầu được tải sau khi xác thực sẽ quyết định thông tin hiển thị

**Phiên hết hạn**

Có sự không khớp giữa thời gian hết hạn phía máy khách và phía máy chủ

**Phiên hết hạn**

Thời hạn sử dụng rất dài

**Kết thúc phiên**

Người dùng có thể buộc chấm dứt phiên của họ

#### Kết thúc phiên

Các phiên bị chấm dứt ở phía máy chủ nhưng việc sử dụng lại phiên cũ sẽ dẫn đến lỗi máy chủ nội bộ

Với tất cả những thông tin này, chúng tôi sẽ báo cáo các lỗ hổng sau đây trong đánh giá bảo mật:

Tuổi thọ phiên quá mức

Chúng ta cũng cần phải điều tra thêm những điều sau đây:

Kiểm soát quyền truy cập trên tất cả các điểm cuối API

Nhật ký ứng dụng web để giải trình các hành động

- Sau khi sua student o cho Cookie thanh Lecturers ta co danh sach hoc sinh

![image](https://github.com/user-attachments/assets/32991eb8-7c20-42f9-9b4b-bfd299d253c9)

- 4 lan Attempts vi

![image](https://github.com/user-attachments/assets/9b64ecc4-05cd-4b1f-9fb4-9fc58027beb9)

![image](https://github.com/user-attachments/assets/9fd4a630-d1a8-4603-a312-17187e85fefc)

- Diem hs 1 cao nhat :

![image](https://github.com/user-attachments/assets/fe3cac00-8120-45fb-97d8-f65fbd7bc714)

![image](https://github.com/user-attachments/assets/13b623af-cc38-4347-a180-073ebeb81981)

![image](https://github.com/user-attachments/assets/1e3d77be-36b0-446a-add0-ff2dc1227772)

Phòng thủ

Để chống lại các cuộc tấn công này, điều quan trọng là phải triển khai vòng đời quản lý phiên an toàn. Mặc dù một số mục đã được đề cập trong phòng này, chúng ta hãy cùng xem lại:

Giá trị của phiên phải được lưu trữ an toàn, bất kể đó là cookie hay mã thông báo.

Bản thân các giá trị phiên phải đủ ngẫu nhiên và không thể đoán được hoặc sử dụng cơ chế ký để đảm bảo chúng không thể bị giả mạo.

Phiên nên được sử dụng để theo dõi hành động của người dùng và thực hiện kiểm tra quyền để đảm bảo người dùng có thể thực hiện hành động được yêu cầu.

Phiên phải hết hạn sau một khoảng thời gian nhất định để tránh việc chúng được sử dụng để truy cập liên tục.

Nếu nút đăng xuất được nhấn, phiên sẽ bị xóa ở phía máy khách và bị vô hiệu hóa ở phía máy chủ. Nếu không, người dùng sẽ không thể hủy phiên của họ nếu nó bị xâm phạm.

