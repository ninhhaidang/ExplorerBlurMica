# ExplorerBlurMica

Thêm hiệu ứng làm mờ nền hoặc Acrylic hoặc Mica cho File Explorer trên win10 và win11

#

\| [Tiếng Việt](/README_VI.md) | [English](/README.md) |
Dự án này sử dụng [LGNU V3 license](/COPYING.LESSER).

[![license](https://img.shields.io/github/license/Maplespe/ExplorerBlurMica.svg)](https://www.gnu.org/licenses/lgpl-3.0.en.html)
[![Github All Releases](https://img.shields.io/github/downloads/Maplespe/ExplorerBlurMica/total.svg)](https://github.com/Maplespe/ExplorerBlurMica/releases)
[![GitHub release](https://img.shields.io/github/release/Maplespe/ExplorerBlurMica.svg)](https://github.com/Maplespe/ExplorerBlurMica/releases/latest) <img src="https://img.shields.io/badge/language-c++-F34B7D.svg"/> <img src="https://img.shields.io/github/last-commit/Maplespe/ExplorerBlurMica.svg"/>

## Hiệu ứng

* Có thể chọn Blur, Acrylic hoặc Mica
* Tùy chỉnh được màu trộn
* Tự động thích ứng chế độ sáng/tối

Dự án này chỉ dành cho Explorer, nếu bạn muốn áp dụng hiệu ứng toàn cục hãy xem dự án khác của chúng tôi [DWMBlurGlass](https://github.com/Maplespe/DWMBlurGlass).

## Tương thích

Tương thích với các phần mềm thay đổi giao diện cửa sổ như StartAllBack, OldNewExplorer.

Cũng tương thích với các theme bên thứ ba.

## Mục lục

* [Xem trước](#xem-truoc)
* [Cách sử dụng](#cach-su-dung)
* [Tệp cấu hình](#tep-cau-hinh)
* [Khác](#khac)

## Xem trước

<details><summary><b>Windows 11</b></summary>

23H2 WinUI3

```ini
[config]
effect=1
clearBarBg=true
clearAddress=true
clearWinUIBg=true
[light]
r=255
g=255
b=255
a=200
....
```

![image](https://github.com/Maplespe/ExplorerBlurMica/blob/main/screenshot/012949.png)

Chế độ tối

```ini
[config]
effect=2
clearBarBg=true
clearAddress=true
clearWinUIBg=true
```

![image](https://github.com/Maplespe/ExplorerBlurMica/blob/main/screenshot/013256.png)

22H2 XamlIslands

```ini
[config]
effect=1
clearBarBg=true
clearAddress=true
clearWinUIBg=true
[light]
r=255
g=255
b=255
a=200
....
```

![image](https://github.com/Maplespe/ExplorerBlurMica/blob/main/screenshot/152834.png)

```ini
[config]
effect=1
clearBarBg=true
clearAddress=true
clearWinUIBg=false
[light]
r=255
g=255
b=255
a=200
....
```

![image](https://github.com/Maplespe/ExplorerBlurMica/blob/main/screenshot/152929.png)

</details>

<details><summary><b>Windows 10</b></summary>

```ini
[config]
effect=1
clearBarBg=true
clearAddress=true
clearWinUIBg=false
[light]
r=222
g=222
b=222
a=200
```

![image](https://github.com/Maplespe/ExplorerBlurMica/blob/main/screenshot/230909.png)

</details>

## Cách sử dụng

### Cài đặt

1. Tải về file nén từ trang [Release](https://github.com/Maplespe/ExplorerBlurMica/releases)
2. Giải nén đến một thư mục, ví dụ: "`C:\Program Files`"
3. Chạy "`register.cmd`" với quyền quản trị viên
4. Mở File Explorer để hiệu ứng có tác dụng

cmd: `regsvr32 "đường_dẫn/ExplorerBlurMica.dll"`

### Gỡ cài đặt

1. Chạy "`uninstall.cmd`" với quyền quản trị viên
2. Xóa các tệp còn lại

cmd: `regsvr32 /u "đường_dẫn/ExplorerBlurMica.dll"`

#

Lưu ý: nếu File Explorer gặp sự cố bất thường hãy giữ phím `ESC` để mở lại Explorer và gỡ cài đặt chương trình này.

## Tệp cấu hình

```ini
[config]
#Loại hiệu ứng: 0=Blur 1=Acrylic 2=Mica 3=Blur(Clear) 4=MicaAlt
#Blur chỉ dùng được trên win11 bản trước 22H2; Blur(Clear) dùng được trên cả win10 và win11; Mica chỉ dùng được trên win11
effect=1
#Xóa nền thanh địa chỉ
clearAddress=true
#Xóa nền thanh cuộn
#(Lưu ý: do thanh cuộn của hệ thống vốn không trong suốt nên để bỏ nền, thanh cuộn được vẽ lại bởi chương trình này, có thể hơi khác giao diện gốc)
clearBarBg=true
#Xóa màu nền của thanh công cụ WinUI hoặc XamlIslands trong Explorer trên Windows 11
clearWinUIBg=true
#Hiển thị đường phân cách giữa TreeView và DUIView
showLine=true
[light]
#Màu khi hệ thống ở chế độ sáng
#Thành phần màu RGBA
r=220
g=220
b=220
a=160
[dark]
#Màu khi hệ thống ở chế độ tối
r=0
g=0
b=0
a=120

```

Sau khi chỉnh sửa và lưu file, mở lại Explorer để có hiệu lực.

## Khác

Phụ thuộc: [minhook](https://github.com/m417z/minhook).

Dự án này tách ra từ thành phần của công cụ tùy chỉnh giao diện Maple [MToolBox](https://winmoes.com/tools/12948.html).
