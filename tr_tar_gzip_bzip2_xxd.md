[1. tr](#tr)

[2. tar](#tar)

[3. gzip](#gzip)

[4.bzip2](#bzip2)

[5. xxd](#xxd)

<a name="tr"></a>

## tr

- dịch, chuyển đổi, xóa, ép lặp kí tự.

- `tr [OPTION] SEP1 [SEP2]`

- Sẽ thay thế mối kí tự, mỗi kí tự cùng vị trí

### Chuyển đổi chữ thường thành chữ hoa.

- `tr abcde ABCDE`

- `tr [:lower:] [:upper:]`

### chuyển không gian trống -> tabs

- `echo "This is for testing " | tr [:space:] '\t'`: '\t': có thể thay thế bất cứ kí tự nào.

### Xóa các số  use -d

- `echo "the geek stuff 111231" | tr -d [:digit:]`: xóa số chỉ còn lại kí tự

### Xóa tất cả các kí tự use -cd

- `echo "my user is 4235235" | tr -cd [:digit:]`: xóa tất cả các kí tự, chỉ còn số

### Hủy bỏ các kí tự k in đc trong 1 file

- `tr -cd [:print:] < file.txt`

<a name=""></a>

## tar

<a name="tar"></a>

- tạo tar lưu trữ

- làm chủ các tập tin

- trích xuất 1 file hoặc thư mục

- xem nội dung lưu trữ

- xác nhận tính toàn vẹn của tar archives

### Tạo 1 kho lưu trữ với tar command (không có nén) use `cvf`

- `tar cvf archive_name.tar dirname/`

> c: tạo 1 new archive

> v: danh sách các file đc xử lí

> f: theo tên kho tệp lưu trữ

### Tạo 1 tar gzip archive use `cvzf`

- `tar cvzf archive_name.tar.gz dirname/` : `.tar.gz` = `.tgz`

### `cvfj` cho bzip2

- `tar cvfj archive_name.tar.bz2 dirname/`: `.tar.bz2` = `.tb2`

- bzip2 mất nhiều thời gian nén và giải nén hơn gzip và size lớn hơn 


<a name=""></a>
<a name=""></a>
<a name=""></a>
<a name=""></a>
<a name=""></a>
