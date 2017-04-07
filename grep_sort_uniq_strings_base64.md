## grep 

- Lọc file, more file

### 1. remove all comment lines:

- `grep -v "#" /etc/apache2/sites-available/befault-ss/`

### 2. Find all .mp3 vs `-i`, `vi`.

- `find . -name "*.mp3" | grep -i JayZ | grep -vi "remix"`

- Use find các file có extension là .mp3, lọc và in ra `-i` của ông Jayz và `không` in ra file (-vi) có chuỗi là "remix".

### Print number of lines around với `-C`

- `ifconfig grep -C 2 lo`

### đếm số dòng của kết quả tìm được vs `-c`.

- `ifconfig | grep -c inet6`

### Hiển thị số dòng trong file của chuỗi tìm kiếm đã ch vs `-n`.

- `grep -n "main"`

### Tìm kiếm 1 chuỗi trong tất cả các thư mục vs `-r`.

- `grep -r "function" *`

### Tìm kiếm cho tất cả các mẫu vs `-w`.

- `ifconfig | grep -w "RUNNING"` : in ra tất cả các line chứa mẫu "RUNNING"

### Tìm kiếm 1 chuỗi cho trước trong 1 file xác định

- `grep "minhnhat" doc.txt`

- mở rộng `grep "minhnhat" *.txt`

### Tìm kiếm không quan trọng trường hợp `the` `ThE` hay `tHe` với `-i`

- `grep -i "string" FILE`

### Kết hợp các biểu thức trong chuỗi tìm kiếm.

- ?, \*, +, {n}, {n,}, {,m}, {m,n}

### Kiểm tra cho 1 chuỗi xác định mà không cho ra kqua các chuỗi con với `-iw`

- vd bạn `grep "is"` nó sẽ ra "his", "ist" -> mọi chuỗi xuất hiện "is".

- muốn tìm chỉ chứa "is" thì `grep -iw`.

### Tạo khoảng cách giữa các kết quả tìm kiếm với `-A`, `-B`, `C`.

- `grep -A 3 -i "string"`.


- `grep -B 4 -i "string"`.

- `grep -C 2 -i "string"`.

##


