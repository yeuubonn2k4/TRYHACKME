### 1. Các câu lệnh cơ bản trong Linux

- echo : In ra văn bản đó

- whoami : Tư cách người dùng nào đang được đăng nhập

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/9cfcc1e6-4e57-475b-99b9-ff24660fd7a2)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/a6ff4311-55f6-4e4c-a651-2265c9dd8b14)

- Các lệnh tương tác với Hệ thống tệp tin

  - ls : liệt kê

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/4e2eae5d-49fe-4a38-93bb-0a8d74ff35f5)

  - cd: chuyển hướng thư mục

 ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/a6c14589-1b79-45e5-9614-64547087cd2e)

  - cat : đọc nội dung

 ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/2d3b9429-e284-4b9f-b40b-78fb3bddf15b)

> Chúng ta có thể đọc nội dung của 1 file khi đang đứng từ 1 thư mục

> Ví dụ : ` cat /home/ubuntu/Documents/todo.txt `

  - pwd : in ra thư mục đang làm việc

> bạn muốn tìm file "Documents" nhưng không biết file đó đang nằm ở đâu nên chúng ta có thể dùng ` pwd ` để biết.

> Sau khi biết đang ở đâu, có thể dùng cd để chuyển hướng đến địa chỉ file đó ` cd /home/ubuntu/Documents `

 ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/ddcbb1b9-3cdd-46b0-95c3-8282754c5b22)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/ce9ed62c-d590-4391-972a-7d1b092b2c88)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/fec5ec40-5296-4374-a951-6bf364cdb834)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/790544b9-1b66-4ca1-8e84-4390bf74b059)
 
![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/d1642dfb-f74a-45c1-b58e-95f819b16b4d)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/b7bf08f3-aa89-4496-9883-db301ae03160)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/9179beba-7f29-4397-9e54-f171a72c676b)

### 2. Tìm kiếm Files

- Find : sử dụng để không phải xem qua từng cái 1 để tìm file đó . Sử dụng để tìm kiếm các tệp cụ thể

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/3106e8dc-15fb-4443-ac8b-7a0831a05332)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/13124e0e-0cab-49d4-aecb-09f9c133375a)

> Sử dụng ` file -name ` *.txt  nếu bạn không biết rõ tên file đó là gì

- grep : lệnh này cho phép chúng ta tìm kiếm nội dung của tệp để tìm các giá trị cụ thể mà chúng ta đang tìm kiếm

Lấy ví dụ, nhật ký truy cập của máy chủ web. Trong trường hợp này, access.log của máy chủ web có 244 mục.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/4ad6a5ef-9f8b-4f6b-bdc9-3c5d41db6c18)

* Sử dụng cat thì sẽ không hiệu quả lắm nên người ta dùng grep để tìm trong tất cả các nội dung để tìm giá trị cụ thể
trong nhật kí log

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/c3d0d434-447f-41d5-ac44-daeef9b43925)

Grep" đã tìm kiếm trong tệp này và đã hiển thị cho chúng tôi mọi mục nhập mà chúng tôi đã cung cấp và mục đó có trong tệp nhật ký IP này.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/e1b1f6d4-10cb-4f2c-8299-5ab95a3b10ab)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/601b2cfe-38a3-4365-bdf0-ce2c6583be54)

### 3. Các toán tử trong Linux

- "&&" toán tử AND trong Linux khi bạn muốn thực thi câu lệnh thứ 2 sau khi câu lệnh thứ 1 thành công, thực thi cùng 1 lúc không giới hạn ở con số 2

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/3c98e803-d4f9-45de-b0cb-8f98e6506771)

- "&" không hề liên quan đến "&&". Nó là 1 opertator nền.

  > ví dụ bạn thực thi 1 lệnh mất tầm 10s, trong suốt 10s này bạn sẽ không thể thực thi bất kì câu lệnh khác. Nhưng bạn vẫn có thể thực thi 1 câu lệnh khác mà không cần chờ câu lệnh kia thực thi xong.
  
   ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/5344e486-cbe2-4aeb-a0d1-23a36731383f)

- "$" dùng để gọi 1 biến trong hệ thống máy tính

  > cú pháp:

  `
  $<Tên-biến>

  ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/75874c8c-c8bd-44b3-9422-a007e4d6b6e0)

Nếu mình dùng lệnh echo $USER, mình đã in ra giá trị được gán với biến USER trong hệ thống. Nếu không có "$" nó sẽ chỉ in ra chữ USER.

> Lưu ý: Linux phân biệt chữ hoa và thường -> $user và $USER là 2 biến hoàn toàn khác nhau

+ Các biến trong hệ thống Linux thường được viết bằng chữ in hoa : USER, HOME, PATH...

+ Phải thay đổi giá trị của variable để năng cấp quyền quản trị.

> Tạo và gán giá trị cho variable

`
<TÊN-BIẾN>=<GIÁ-TRỊ-CẦN-GÁN>

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/56b5f6a9-86d5-40a9-9d1a-1e833373424b)

+ Để thay đổi giá trị của 2 biến trên, dùng lệnh ` expore ` ( lệnh này không tra cứu bằng man export được) nhưng có thể tra cứu bằng

+ ` export --help `

  - Thay đổi giá trị đã gán
 
  ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/e5bcd360-e164-4e28-8095-b65ff4e118f3)

> export <TÊN-BIẾN>=<GIÁ-TRỊ-MỚI>


+ Ngoài ra có thể dùng lệnh export để tạo variable :

  > export tên-biến-cần-tạo=giá-trị-gán

  ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/dc5ac939-37a1-4639-979e-dde1bed9e908)

- "|" : pipe line, sử dụng output của command đứng trước làm input cho command đứng sau nó

  ![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/b3840fe3-e3f5-4a64-a7b6-155339d111d3)

- ";" : hoạt động tương tự như "or"

- ">" : Toán tử này là một bộ chuyển hướng - nghĩa là chúng ta có thể lấy đầu ra từ một lệnh (chẳng hạn như sử dụng cat để xuất một tệp) và chuyển nó đi nơi khác. (Về cơ bản, điều này có nghĩa là chúng ta lấy đầu ra từ một lệnh chúng ta chạy và gửi đầu ra đó đến một nơi khác.)

Ví dụ: Một ví dụ tuyệt vời về điều này là chuyển hướng đầu ra của lệnh echo mà chúng ta đã học trong Nhiệm vụ 4. Tất nhiên, chạy một cái gì đó chẳng hạn như echo howdy, sẽ trả lại "howdy" cho thiết bị đầu cuối của chúng tôi - điều đó không hữu ích lắm. Thay vào đó, những gì chúng ta có thể làm là chuyển hướng "xin chào" sang một thứ gì đó chẳng hạn như một tệp mới!

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/7a51ca52-5a95-40f8-90e7-324d1384b6a6)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/8fabebaa-7428-4446-8fdf-c3a092c8f59c)

- ">>" : Toán tử này thực hiện chức năng tương tự của toán tử > nhưng nối thêm đầu ra thay vì thay thế (có nghĩa là không có gì bị ghi đè)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/2fe3937b-1aa4-4d59-94f3-d321579fc005)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/b856cf12-d3e8-43f5-9655-c7000be48e6a)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/8cdd2964-ed25-4b8c-91b6-e568b59c8459)
