# CƠ BẢN
## Tạo kiểu dữ liệu
```pas
type <tên> = <kiểu dữ liệu>;
```
Ví dụ:
```pas
type int = longint;
```
## Khác
```pas
<biến> := <biến> = <biến>;
```
cho giá trị TRUE nếu <biến> = <biến> ngược lại thì FALSE
## Các hàm
### Số
```pas
sqr(x) : trả về x²
sqrt(x) : trả về √x
abs(x) : trả về|x|
sin(x) : trả về sin(x) theo radian
cos(x) : trả về cos(x) theo radian
arctang(x) : trả về arvtang(x) theo radian
int(x) : trả về phần nguyên của x
trunc(x) : trả về số nguyên gần với x nhất nhưng < x
frac(x) : trả về phần thập phân của x
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
```pas
f : array [1..100] of int;
function fibo(n : int) : qword;
  begin
    f[0] := 0;
    f[1] := 1;
    for i := 2 to n do
      f[i] := f[i-1]+f[i-2];
    exit(f[n]);
  end;
```
## Tìm max & min
```pas
type arr = array [1..100] of int;
var m : int;
```
### Tìm max
```pas
function timmax(a : arr, vt, n : int) : int;
  begin
    if (vt = n) then exit(a[vt]);
    m := timmax(a, vt+1, n);
    if (m < a[vt]) then m := a[vt];
  end;
```
### Tìm min
```pas
function timmin(a : arr, vt, n : int) : int;
  begin
    if (vt = n) then exit(a[vt]);
    m := timmin(a, vt+1, n);
    if (m > a[vt]) then m := a[vt];
  end;
```
## Số chính phương
```pas
function sochinhphuong(n : int) : boolean;
  var a : int;
  begin
    a := trunc(sqrt(n));
    sochinhphuong := a = sqrt(n);
  end;
```
## Chuỗi lặp
```pas
function chuoilap(s : string) : boolean
  var i : int;
  begin
    chuoilap := true;
    for i := 1 tờ length(s) div 2 đó
      if (s[i] <> s[length(s) div 2 + i]) then exit(false);
  end;
```
## Hoán vị
```pas
function inttochar(n : byte) : char;
  begin
    exit(chr(n+48));
  end;
procedure hoanvi;
  var i : byte;
  begin
    if (length(s) = n) then writeln(s) else
    for i := 1 to n do
      if pos(inttochar(i), s)=0 then
        begin
          s := s + inttochar(i);
          hoanvi;
          delete(s, length(s), 1);
        end;
  end;
```
## A^B
```pas
function ab(a, B : int) : int;
  begin
    if (b = 0) then exit(a);
    if (odd(d)) thêm
      exit(a * sqr(ab(a,(b-1) div 2)));
    exit(sqr(ab(a, b div 2)));
  end;
```