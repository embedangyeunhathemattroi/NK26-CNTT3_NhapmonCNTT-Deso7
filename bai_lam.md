# BÀI LÀM – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:**Phạm Ngọc Linh
- **Lớp:**K26CNTT3
- **Link repository:**https://github.com/embedangyeunhathemattroi/HN-K26-CNTT3_Nhapmon-CNTT-Deso07
- **Hệ điều hành (Windows/macOS):**Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Force
mv .\lich_lam_viec.txt .\docs\
mkdir backup
cp .\data\hoa_don_spa_thang_7.xlsx .\backup\
rm -LiteralPath .\temp_707.tmp
cd .\logs
ls -Force
cd ..
Get-ChildItem -Recurse -Force

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text

    Directory: C:\Users\TRONG TIN\Downloads\starter-kit (5)\starter-kit\spa-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026  10:50 AM                backup
d-----        11/11/2026  10:45 AM                data
d-----        11/11/2026  10:50 AM                docs
d-----        11/11/2026  10:45 AM                evidence
d-----        11/11/2026  10:46 AM                logs
d-----         11/3/2026   7:07 AM                web
-a----         11/3/2026   7:07 AM             75 .env
-a----        11/11/2026  10:50 AM           2641 bai_lam.md


    Directory: C:\Users\TRONG TIN\Downloads\starter-kit (5)\starter-kit\spa-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6149 hoa_don_spa_thang_7.xlsx


    Directory: C:\Users\TRONG TIN\Downloads\starter-kit (5)\starter-kit\spa-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6149 hoa_don_spa_thang_7.xlsx


    Directory: C:\Users\TRONG TIN\Downloads\starter-kit (5)\starter-kit\spa-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            149 lich_lam_viec.txt


    Directory: C:\Users\TRONG TIN\Downloads\starter-kit (5)\starter-kit\spa-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            939 service.log


    Directory: C:\Users\TRONG TIN\Downloads\starter-kit (5)\starter-kit\spa-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         11/3/2026   7:07 AM                images
-a----         11/3/2026   7:07 AM            597 app.js
-a----         11/3/2026   7:07 AM            523 index.html
-a----         11/3/2026   7:07 AM            460 style.css


    Directory: C:\Users\TRONG TIN\Downloads\starter-kit (5)\starter-kit\spa-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           3091 logo-lotuscare.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
Get-Content .\logs\service.log | Select-String "status=500" > .\logs\loi_500.txt
Get-Content .\logs\loi_500.txt -TotalCount 2


```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-07-28 08:12:50 POST /api/dat-lich status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
Get-Content .\logs\service.log | Select-String "status=404" | Measure-Object


```

```text
Count    : 4
Average  :
Sum      :
Maximum  :
Minimum  :
Property :


```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
Dang tao bao cao...
Hoan thanh!

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | network |lỗi hình ảnh logo.png  |tại index.html sửa tại dòng 10  thành logo-lotuscare.png   |
| 2 | console |Uncaught ReferenceError: hienThiGoiDichVu is not defined  |tại app.js sửa tại dòng 18 từ hienThiGoiDichVu thành hienThiGoiSpa  |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:**Mở web/index.html bằng Chrome trên Windows, bật Console và Network rồi  tải lại trang.
- **Expected:**Bảng tính hóa đơn spa hiển thị dữ liệu .
- **Actual:**Bảng chỉ hiện tiêu đề cột.
- **Log:**Uncaught ReferenceError: hienThiGoiDichVu is not defined

### Câu tìm kiếm Google

```text
site:stackoverflow.com "Uncaught ReferenceError"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/hoa_don_spa_thang_7.xlsx`, không cần ghi vào đây.
