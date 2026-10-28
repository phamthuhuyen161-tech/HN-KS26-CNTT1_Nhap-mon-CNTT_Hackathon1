# BÀI LÀM – HACKATHON 01

- **Mã đề:** 15
- **Họ tên:** Phạm Thu Huyền
- **Lớp:** CNTT2
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
get-location
get-childitem -recurse -force
mv "bang_gia_goi.txt" docs
mv "logo_studio_anh.PNG" media
cp "media\logo_studio_anh.PNG" backup
rm "temp_238.tmp"
set-location
get-childitem -recurse -force
cd..

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Directory: C:\Users\ADMIN\Downloads\starter-kit (1)\starter-kit


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026   1:47 PM                Studio Anh Website FINAL
------        10/27/2026   1:32 AM           2225 bai_lam.md


    Directory: C:\Users\ADMIN\Downloads\starter-kit (1)\starter-kit\Studio Anh Website FINAL


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026   1:47 PM                backup
d-----        10/28/2026   1:39 PM                data
d-----        10/28/2026   1:45 PM                docs
d-----        10/28/2026   1:40 PM                logs
d-----        10/28/2026   1:46 PM                media
------        10/27/2026   1:32 AM             71 .env
-a----        10/27/2026   1:32 AM           2225 bai_lam.md


    Directory: C:\Users\ADMIN\Downloads\starter-kit (1)\starter-kit\Studio Anh Website FINAL\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           7231 logo_studio_anh.PNG


    Directory: C:\Users\ADMIN\Downloads\starter-kit (1)\starter-kit\Studio Anh Website FINAL\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           6099 lich_chup_thang5.xlsx.xlsx


    Directory: C:\Users\ADMIN\Downloads\starter-kit (1)\starter-kit\Studio Anh Website FINAL\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM             59 bang_gia_goi.txt


    Directory: C:\Users\ADMIN\Downloads\starter-kit (1)\starter-kit\Studio Anh Website FINAL\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           1088 studio.log.log


    Directory: C:\Users\ADMIN\Downloads\starter-kit (1)\starter-kit\Studio Anh Website FINAL\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           7231 logo_studio_anh.PNG

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
get-content "logs/studio.log" | select-string "ERROR" >>.logs/daily_report.txt
get-content "logs/daily_report.txt" totalcount 2

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-05-28 07:29:30 [ERROR] Tai anh len may chu that bai
2026-05-28 07:44:30 [ERROR] Tai anh len may chu that bai


```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
./auto_report.ps1

```

### Kết quả hiển thị

```text
Dang loc log ...
Hoan thanh!

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
get-content "logs/studio.log" | select-string "ERROR" | measure-object

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
Count    : 7

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
"=== TONG HOP LOG ===" > logs/tong_hop.txt
gc logs/studio.log | select-string "WARNING" >> logs/tong_hop.txt
gc logs/studio.log | select-string "ERROR" | measure-object | select-object .count >> logs/tong_hop.txt 
```

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG ===

2026-05-28 07:26:30 [WARNING] Thoi gian tai trang cham
2026-05-28 07:35:30 [WARNING] Lich chup cuoi tuan sap kin
2026-05-28 07:53:30 [WARNING] Thoi gian tai trang cham



.count
------
      

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/lich_chup_thang_5.xlsx`, không cần ghi vào đây.
