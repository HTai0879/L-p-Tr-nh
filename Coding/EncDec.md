```pas
program EncDec;
uses crt;
type int = longint;
var id : string;
procedure inp;
  begin
    clrscr;
    write('Nhập vào ID máy: '); readln(id);
  end;
function encryption(id : string) : string;
  var i : int;
  e : string;
  begin
    for i := 1 to length(id) do
      e := e + (chr(ord(id[i])+(length(id)-i)));
    for i := 1 to length(e) do
      case e[i] of
        'A'..'z' : encryption := encryption + e[i];
      end;
  end;
function decryption(id : string) : string;
  var i : int;
  e : string;
  begin
    for i := 1 to length(id) do
      e := e + (chr(ord(id[i])-(length(id)-i)));
    for i := 1 to length(e) do
      case e[i] of
        'A'..'z' : decryption := decryption + e[i];
      end;
  end;
procedure out;
  begin
    writeln('Enc : ', encryption(id));
    writeln('Dec : ', decryption(id));
  end;
begin
  inp;
  out;
  readln;
end.

```