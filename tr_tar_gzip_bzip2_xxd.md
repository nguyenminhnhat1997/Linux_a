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

### Extract (untar) an archive use tar command

- extract a `*.tar` file use `xvf`

- `tar xvf archive_name.tar`

### Extract a gzip tar archive (\*.tar.gz) use `xvzf`

- `tar xvfz archive_name.tar.gz`

### Extracta bzip tar archive (\*.tar.bz2) use `xvjf`

- `tar xvfj archive_name.tar.bz2`

### Liệt kê danh sách 1 archive use tar command

- 1. Xem nội dung mà không extract use `tvf`

- `tar tvf archive_name.tar`

- 2. Xem `\*.tar.gz` mà không extract use `tvzf`

- `tar tvzf archive_name.tar.gz`

- 3. Xem `\*.tar.bz2` mà không extract use `tvjf`

- `tar tvjf archive_name.tar.bz2`

### extract 1 single file từ tar, tar.gz, tar.bz2 file 

- `tar xvf archive_name.tar /path/to/file`

- `tar xvfz archive_name.tar.gz /path/to/file`: gzip

- `tar xvfj archive_name.tar.bz2 /path/to/file` : bzip2

### Extract a single directory từ tar, tar.gz, tar.bz2 file cùng với thư mục con lun

- `tar xvf archive_file.tar /path/to/dir/`

- `tar xvf archive_file.tar /path/to/dir1 /path/to/dir2/`: nhiều directory

- `tar xvfz archive_file.tar.gz /path/to/dir`: gzip

- `tar xvfj archive_file.tar.bz2 /path/to/dir`: bzip2

### Extract nhóm của các file tar, tar.gz, tar.bz2 

- `tar xvf archive_file.tar --wildcards '*.pl'`

### Thêm 1 file or directory đến 1 archive hiện có use `-r`

- `tar rvf archive_name.tar newdir/`

### Xác minh file có sẵn in tar use `-W`

- `tar cvfW file_name.tar dir/`

### Xác minh trước khi remove a directory/file từ 1 archive file or từ file systom

- `tar tvfW file_name.tar`

### Tìm điểm khác nhau giữa gzip archive file và file system

- `tar dfz file_name.tgz`

### Tìm khác nhau giữa bzip2 archive file and file 
<a name=""></a>
<a name=""></a>
<a name=""></a>
<a name=""></a>
<a name=""></a>
