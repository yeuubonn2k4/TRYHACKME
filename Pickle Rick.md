- Quet Nmap ta thay duoc 2 cong

![image](https://github.com/user-attachments/assets/eaa10548-4d6f-4162-86b2-7f7131a814c1)

- Xem ma nguon ta thay co username

![image](https://github.com/user-attachments/assets/aeeaa657-384b-431d-9838-be346cf08584)

- Mình sẽ sử dụng Gobuster để tìm thêm một số file hoặc directory ẩn:

gobuster dir -u http://10.10.245.218/ -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt -t 20 -x php,txt,html

Gobuster sẽ sử dụng wordlist để dò các directory ẩn trên IP, đồng thời thử thêm cả đuôi file php, txt, html.

![image](https://github.com/user-attachments/assets/0cbec98e-1a4a-4233-8a85-9784ae69feee)

![image](https://github.com/user-attachments/assets/87081490-f605-4dfb-824b-358779586bdf)

![image](https://github.com/user-attachments/assets/f429b40c-a4bc-489d-a579-cb9a7c7a52ea)

![image](https://github.com/user-attachments/assets/139464d5-58c3-4131-b55b-256c1ad8b55a)
