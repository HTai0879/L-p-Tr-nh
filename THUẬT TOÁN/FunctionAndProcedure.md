# CƠ BẢN
## Tạo kiểu dữ liệu
```pas
type <tên> = <kiểu dữ liệu>;
```
Ví dụ:
```pas
type int = longint;
```
# THUẬT TOÁN
## Giai thừa
'''pas
function giaithua(n: int) : qword;
  begin
    if (n <= 1) then exit(1);
    giaithua := n * giaithua(n-1);
  end;
'''