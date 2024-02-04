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
round(x) : làm tròn số nguyên x
pred(n) : trả về giá trị trước n
succ(n) : trả về giá trị sau n
odd(n) : cho giá trị TRUE nếu n là số lẻ
inc(n) : tăng n thêm 1 đơn vị
inc(n, x) : tăng n lên x đơn vị
dec(n) : giảm n thêm 1 đơn vị
dec(n, x) : giảm n thêm x đơn vị
```
### Sâu
```pas
delete(s, vt, n) : xóa đi n kí tự của sâu s kể từ kí tự thú vật
insert(r, s, vt) : chèn sâu r vào sâu s bắt đầu từ vị trí vt
length(s) : cho độ dài sâu s
copy(s, vt, n) : copy n kí tự của sâu s từ vị trí vt
pos(r, s) : vị trí xuất hiện đầu tiên của r trong sâu s, nếu không xuất hiện thì xuất bằng 0
upcase(s hoặc s[i]) : in hoa sâu s hoặc kí tự s[i]
lowercase(s hoặc s[i]) : chuyển in hoa thành in thường
concat(S1..Ăn) : ghép sâu từ S1 đến An
str(n, s) : chuyển giá trị kiểu số n sáng thành sâu s
val(st, n, e) : sâu st thành số n *bắt buộc thêm e kiểu dữ liệu integer
ord(s) : lấy mã ASLL của 1 kí tự
chr(n) : trả về kí tự tương ứng của n với mã ASLL
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
## Chuyển số sáng char
```pas
function inttochar(n : byte) : char;
  begin
    exit(chr(n+48));
  end;
```
## Hoán vị
```pas
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
### Công thức
![alt](https://freetuts.net/upload/tut_post/images/2020/05/19/2681/cong-thuc-truy-hoi-freetuts.png)
```pas
function ab(a, B : int) : int;
  begin
    if (b = 0) then exit(a);
    if (odd(d)) thêm
      exit(a * sqr(ab(a,(b-1) div 2)));
    exit(sqr(ab(a, b div 2)));
  end;
```
# BÀI TẬP • CÔNG THỨC
### Công thức tính tổng các số chia hết cho k từ 1 đến n
```pas
n := n - (n mod k);
s := (k+n) * ((n-k) div k + 1) div 2;
```