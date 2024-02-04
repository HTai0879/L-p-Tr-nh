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
### n!
```pas
function giaithua(n : int) : qword;
  begin
    if (n <= 1) then exit(1);
    giaithua := n * giaithua(n-1);
  end;
```
### n!!
```pas
function giaithua(n : int) : qword;
  begin
    if (n <= 1) then exit(1);
    giaithua := n * giaithua(n-2);
  end;
```
## Fibonacci
### Đệ quy
```pas
function fibo(n : int) : qword;
  begin
    if (n = 0) then exit(0) else
    if (n = 1) then exit(1);
    exit(fibo(n-1)+fibo(n-2));
  end;
```
### Quy hoạch động
