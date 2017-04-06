## ls

- Liệt kê thông tin về file

### Liệt kê file sử dụng ls với no option 

- ls

- Chỉ liệt kê ra tên, chúng ta không thể xem chi tiết như type, size, ngày sửa đổi và thời gian, quyền và các liên kết

### Liệt kê file với lựa chọn `-l`

- ls -l

- show file or directory, size, ngày tháng và thời gian sửa đổi, tên file and directory, chủ sở hữu file, và quyền truy cập.

### Liệt kê file với lựa chọn `-a`(xem file ẩn)

- ls -a

- file ẩn băt đầu với dấu `.`

### Liệt kê file với định dạng mà con người có  thể đọc đc với option `-lh`.

 - ls -lh
 
- show kích thước ở định dạng mà con người có thể đọc đc

### List file and directory với dấu `/` ở cuối

- ls -F

- use `-F` sẽ thêm `/` ở cuối mỗi directory

### Liệt kê tập tin và thư mục theo thứ tự ngược lại 

- ls -r

### list cây thư mục 

- ls -R

### Hiển thị danh sách các file trong directory

- ls -l /tmp

### Hiển thị thông tin của thư mục

- ls -ld /tmp

### show list chỉnh sửa mới nhất của file or directory

- ls -ltr

### sắp xếp theo kích thước file 

- ls -lS

### Hiển thị số inode number

- ls -i

### show version của command 

- ls --version

### Hiển thị UID và GID của file

- ls -n

## cd

- Chuyển đên 1 **thư mục** nào đó

> **cd**: $home directory

>  **cd ~**: $home directory

> **cd ./**: root

> **cd ..**: thư mục cha

> **cd /nhat**: directory /nhat

> **cd my\ image**.

> **cd "my image"**.

> **cd 'my image'**.


## cat

- Hiển thị nội dung của file text

- Kết hợp nhiều file vào 1 file 

- ! Không chấp nhận thư mục

> **cat -b**: thêm số dòng (không thêm dòng trống).

> **cat -n**: thêm số dòng cho tất cả các dòng.

> **cat -s**: gọp các dòng trống thành 1 dòng.

> **cat -E**: hiển thị $ ở cuối dòng.

> **cat -T**: hiển thị ^| thay vì tabs.

> **cat test1.txt test2.txt > test3.txt**: gọp 2 file thành 1 file.

## find

- Tìm quyền truy cập, quyền sở hữu của người dùng, thay đổi thời gian, kích thước ....

### Danh sách các file trong thư mục 

> **find**: hiển thị tất cả các file trong thư mục hiện tại, và các thư mục con.

> **find . -print**: tương tự như find.

### Tìm kiếm các file trong 1 thư mục or đường dẫn.

> **find ./test**: tìm kiếm file trong 1 thư mục test.

> **find ./test -name "abc.txt"**: tìm kiếm theo tên file(abc.txt) trong thư mục test.

- find ./test -name "\*.txt": có thể sử dụng wilcards.

- find ./test -iname "\*.tXt": tìm kiếm bỏ qua 1 số lỗi nhỏ.

### Gioi hạn kết quả.

- find ./test -maxdepth 2 -name "\*.php": tìm kiếm giới hạn kết quả(-maxdepth), ở đây chỉ xuất hiện 2 kqủa.

### -not or !

- find ./test -not -name "\*.php" = (find ./test ! -name "\*.php"): tìm kiếm loại trừ file .php -> cho kq k có fike .php.

- find ./test -name "abc\*" ! -name "\*.php": tìm kiếm nhiều tiêu chuẩn, ở đây là file bắt đầu với abc và không có phần mở rộng là .php

### Kết hợp nhiều tiêu chuẩn tìm kiếm.

- Khi ta kết hợp nhiều tiêu chuẩn tìm kiếm thì giữa những tiêu chuẩn đó là phép AND muốn sử dụng phép `or` thì thêm lựa chọn `o`

- find ./test -name "\*.php" -o -name "\*.txt": ví dụ cho minh họa ở trên

### Tìm kiếm chỉ 1 file or chỉ 1 thư mục

- find ./test -name "abc\*"

- find ./test -type f -name "abc\*": tìm kiếm only file 

- find ./test -type d -name "abc\*": tìm kiếm only directory

### Tìm kiếm nhiều thư mục cùng 1 lúc

- find ./test ./test2 -type f -name "abc\*"

### Tìm kiếm file ẩn

- find ~ -type f -name ".\*"

### Tìm file với 1 quyền nhất định

- find ./test -type f -perm 0777

- find ./test -type f ! -perm 0777

### Tìm tập tin chỉ đọc

- find /etc -maxdepth 1 -perm /u=r 

### Tìm file thực thi đc

- find /bin -maxdepth 2 -perm /a=x

### Tìm file thuộc về người dùng cụ thể nào đó

- find . -user minhnhat

- find . -user minhnhat -name "\*.php": chúng ta cũng có thể tìm tên của file với các tiêu chí liên quan đến user

### Tìm file thuộc về 1 group nào đó

- find /var/www -group 4Tower

### Tìm file với `~`

- find ~ -type f -name "kyras.txt"

### Tìm file đã sữa đổi sau N ngày trở lại

- find / -mtime 50

### Tìm file đã truy cập trong N ngày qua

- find / -atime 50

### Tìm file đã sữa đổi trong 1 khoảng ngày xác định

- find / -mtime +50 -mtime -100: từ 50-100 day

### Tìm file đã thay đổi trong 1 hour trước

- find /home -mmin -60

### Tìm file đã thay đổi trong N phút trước

- find /home -cmin -60

### Tìm file đã truy cập trong 1 hour qua

- find / -amin -60

### Tìm file or directory dựa trên kích thước 

- find / -size 50M: dựa vào size

- find / -size +50M -size -100M: 1 khoảng xác định

### Tìm các file or directory rỗng 

- find /tmp -type f -empty (file rỗng)

- find ~/ -type d -empty (all directory rỗng)

### Liệt kê ra các tập tin đã tìm thấy

- find -exec ls -ld {} \;

### Xóa tất cả các file or directory phù hợp

- find /tmp -type f -name "\*.txt" -exec rm -f {} \;

- find /home/bob/dir -type f -name \*.log -size +10M -exec rm -f {} \;

## du

- Kiểm tra việc sử dụng đĩa của các file and directory trên 1 máy

- cho biết thông tin nội dung, kích thước của file anđ directory
### Sử dụng du

1.

- Hiển thị tóm lượt cách sử dụng đĩa của thư mục, và thư mục con của chúng

- số đằng trước hiển thị số lượng các khối đĩa 

- du /home

2.

- sử dụng thêm `-h` để thấy đc định dạng mà chúng ta có thể đọc được

- du -h /home

3.

- Tóm tắt toàn bộ kích thước của direntory sử dụng thêm `-s`.

- du -sh /home 

4.

- du -a /home

- Hiển thị tất cả việc sử dụng đĩa của các file và thư mục  với `-a`

- Tương tự ta sử dụng thêm `h` để hiện thị thông số mà con người hiểu đc 

- du -ah /home

5.

- Tính toán và hiển thị việc sử dụng đĩa của tất cả các file và thư mục, nhưng loại trừ file mà người dùng quy định với option `--exclude`

- du -ah --exclude="\*.txt" /home

5.

- Hiển thị việc sử dụng đĩa dựa trên việc thay đổi thời gian với `-time`

- du -ha --time /home


