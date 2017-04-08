[1. grep](#grep)

[2. sort](#sort)

[3. uniq](#uniq)

[4. strings](#strings)

[5. base64](#base64)

<a name="grep"></a>

## ~> grep 

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

### Tìm kiếm tất cả các file trong thư mục hiện tại và thư mục con của nó với `-r`.

- `grep -r "string" *`

### Tìm kiếm trên 1 dòng các chuỗi có trong file thì -> trống, không có -> nội dung có trong file đó vs `-v`.

- `grep -v "string" file`

### Hiển thị dòng không khơp với các mẫu đc đưa ra.

- `grep -v -e "string1" -e "string2"`

### Hiển thị chỉ tên file vs `-l`

- `grep -l this demo_*`

### show ra chỉ 1 chuỗi use `-o`

- `grep -o "is.*line" demo_file`

### show số dòng kết quả use `-n`

- `grep -n "go" demo_text`

<a name="sort"></a>

## ~> sort

- Sắp xếp nội dung của 1 file theo 1 thứ tự cụ thể.

### Mặc định sắp xếp theo mã ascii

- `sort file`

### Loại bỏ các nội dung trùng lập, chỉ hiển thị 1

- `sort -u file`

### Sắp xếp số với `-n`.

- `sort -n file`

### Sắp xếp nhiều file cùng 1 lúc

- `sort -n file1 file2`

### Sắp xếp nhiều file và xóa các bản trùng nhau

- `sort -nu file1 file2`

### sort file on the basis of 1st field

- `sort -t"," -k1,1 file`

- `sort -t"," -k2,2 file`

- `sort -t"," -k1nr,1 file`

<a name="uniq"></a>

## uniq

- Loại bỏ or phát hiện bản sao

- Syntax: `uniq [-option]`

### Mặc định sẽ remove các dòng trùng lập in file.

- `uniq file`

### Đếm số lần trùng lập use `-c`.

- `uniq -c file`

### Chỉ in các dòng có sự trùng lập trong file use `-d` `-D`.

- `uniq -d file`

### In dòng không có sự trùng lập use `-u`.

- `uniq -u file`

### So sánh hạn chế với n kí tự đầu tiên use `-w`.

- `uniq -c -w 8 file`: chỉ so sánh 8 kí tự đầu tiên của dòng

### Không so sánh n kí tự đầu tiên của dòng use `-s`.

- `uniq -s 2 file`: bỏ qua 2 kí tự đầu k so sánh

- `-f`: cũng tương tự nhưng nó bỏ qua cụm, vd: abc_bcc_asz -> `-f 1` bỏ qua abc chỉ so sánh 2 cái sau.

<a name="strings"></a>

## strings

- Tìm kiếm trong file binary cho 1 chuỗi xác định.

- Mặc định (strings file_binary) chỉ hiển thị những kí tự in được từ các đoạn zữ liệu của object file

- Muốn tìm kiếm đầy đủ file -> use `-q`

- `strings -s file_binary`

### Tìm kiếm thông tin bản quyền.

- `strings /bin/ls | grep Copyright`

### Use strings trên nhiều file

- `strings -f /bin/* | grep Copy`

- `-f`: hiện đường dẫn của kqua ở trước mỗi dòng.


