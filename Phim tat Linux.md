#Phím tắt Linux

###1.Trong terminal
* **`<Ctrl> + L`**: xoá toàn bộ màn hình, giống lệnh clear
* **`<Ctrl> + D`**: exit session, giống lệnh exit
* **`<Ctrl> + R`**: tìm một lệnh đã chạy trước đây, nhấn <Ctrl> + R sau đó bắt đầu gõ một phần của câu lệnh, hệ thống sẽ tự hoàn tất phần còn lại dựa trên các câu lệnh đã được thực hiện trước đó
* **`<Tab>`**: tự động hoàn tất câu lệnh
* **`<Shift> + <Insert>`**: dán (paste) nội dung đã copy vào terminal
* **`<Shift> + PageUp`**: cuộn màn hình lên trên một trang
* **`<Ctrl> + <Alt> + F2 (<Alt> + F2>`** nếu đang ở chế độ console): chuyển sang virtual terminal thứ 2, tương tự với F3, F4 ...

###2. Trong GNOME

* **`<Ctrl> + <Alt> + D`**: hiển thị desktop, giống <Windows> + D trong Windows
* **`<Ctrl> + <Alt> + <Left/Right>`**: chuyển sang workspace trước/kế tiếp
* **`<Ctrl> + W`**: đóng cửa sổ hiện thời
* **`<Ctrl> + Q`**: thoát khỏi chương trình hiện thời
* **`<Alt> + F1`**: Hiển thị main menu
* **`<Alt> + F2`**: Hiển thị hộp thoại chạy dòng lệnh, giống <Windows> + R trong Windows
* **`<Alt> + F5`**: Bỏ phóng to cửa sổ hiện thời
* **`<Alt> + F9`**: Thu nhỏ <minimize> cửa sổ hiện thời
* **`<Alt> + F10`**: Phóng to <maximize> cửa sổ hiện thời

###3. Trong OpenOffice:

* **`<Ctrl> + <Shift> + B`**: chuyển font sang dạng subscript, giống <Ctrl> + '+' trong MS Word
* **`<Ctrl> + <Shift> + P`**: chuyển font sang dạng supperscript, giống <Ctrl> + <Shift> + '+' trong MS Word
* **`<Ctrl> + 1`**: Single line spacing
* **`<Ctrl> + 2`**: Double line spacing
* **`<Ctrl> + 5`**: 1.5 line spacing

Xem danh sách chi tiết các phím tắt của OpenOffice tại http://www.entropy.ch/software/macos...shortcuts.html

###4. Trong vi (vim)

Các phím sau đây được sử dụng trong chế độ nhập lệnh (không phải chế độ nhập văn bản). Để viết về vi thì cần một bài riêng, nên ở đây hanz2811 chỉ nêu ra một số phím/lệnh chính, chú ý các phím/lệnh sau đây có phân biệt chữ hoa và chữ thường:
* `G`: tới cuối file
* `#G`: tới dòng thứ # (ví dụ 10G, 100G)
* `H`: tới đầu trang
* `dd`: xóa dòng hiện thời
* `yy`: copy dòng hiện thời
* `p`: dán xuống dòng dưới dòng hiện thời
* `P`: dán vào trước vị trí con trỏ
* `/`: bắt đầu tìm kiếm
* `^`: tới đầu dòng
* `$`: tới cuối dòng
* `%`: tới dấu đóng (mở) ngoặc tương ứng
* `%s/old_text/new_text/g`: thay thế tất cả các old_text bằng new_text
* Ở chế độ nhập văn bản, gõ `<Ctrl> + P` để sử dụng auto text completion

++++++++++

Các câu lệnh hữu ích trong quá trình làm quen với Linux
1. chuyển stderr và stdout vào cùng một file, thêm đoạn sau vào cuối câu lệnh 2>&1 output.log
2. để ghi stdout của chương trình vào file bên cạnh việc in ra màn hình, thêm đoạn sau vào sau câu lệnh | tee output.log
3. truy cập x từ xa, dùng lệnh ssh -X user@remote.host
trên máy remote host cần có các nội dung sau trong file /etc/ssh/sshd_config


Code:

`change: X11Fowrading to yes`<br> 
`change X11DisplayOffset 10` <br>
 `change X11Uselocalhost yes`




4. tìm và thay thế xâu ký tự trong nhiều file (có dấu ; ở cuối) find ./ -type f -exec sed 's/string1/string2' {} \;
5. thay thế tất cả các xâu OLD bằng xâu NEW trong vim :%s/OLD/NEW/g
6. theo dõi thời gian thực hiện của một câu lệnh (tùy chọn v yêu cầu hiện thị chi tiết) /usr/bin/time -v -- <command to execute>
7. hiển thị các file có thể chạy được trong thư mục hiện thời bằng ls ls -F | grep \*
8. sửa file đầu tiên trong thư mục vi `ls | head -1`
9. tar -jxf file_name.tar.bz2 giải nén file tar dạng bz2, tar -zxf file_name.tar.gz giải nén file tar dạng gz
10. tar -jcf file_name.tar.bz2 file_to_archive nén file dạng bz2, tar -zcf file_name.tar.gz file_to_archive nén file dạng gz
11. which <command> hiển thị đường dẫn đầy đủ tới câu lệnh <command>
12. file <filename> xác định xem filename là kiểu file gì
13. md5sum kiểm tra mã md5 hash của một file, xâu ký tự
14. id hiển thị thông tin về người dùng và các nhóm của người dùng đó (chi tiết hơn whoami)
15. dùng su - username để impersonate một người dùng khác
16. dùng sudo su - để chuyển lên account root và có các setting dành cho root
17. df -h để kiểm tra dung lượng ổ đĩa cứng, dùng du -h để kiểm tra dung lượng của thư mục hiện thời và các thư mục con trong đó, dùng du -sh để chỉ hiện thị dung lượng của thư mục hiện thời (không hiện chi tiết về các thư mục con)
18. cat /proc/cpuinfo hiển thị thông tin về hệ thống (tốc độ, bộ nhớ, kiến trúc máy ...)
19. free -m hiển thị thông tin về tình trạng sử dụng bộ nhớ trên máy theo megabytes
20. diff file1 file2 so sánh nội dung hai file
21. dùng ls -lh thay cho ls -l 
22. cat file_name | wc -l đếm số dòng trong một file
23. uname -r xem phiên bản của Linux kernel
24. find . | xargs grep 'string' tìm các file có chữa chuỗi string trong thư mục hiện thời
25. watch <command> chạy và hiển thị kết quả của lệnh command sau mỗi 2s. Bấm Ctrl+C để kết thúc
26. w xem danh sách những người đang login vào hệ thống
27. lsof | grep <command> xem danh sách các file mà command đang truy cập
