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

### Xóa tất cả các digits từ string use 


<a name=""></a>
<a name=""></a>
<a name=""></a>
<a name=""></a>
<a name=""></a>
<a name=""></a>
