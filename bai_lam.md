# BÀI LÀM – HACKATHON 02

- **Mã đề:** 08
- **Họ tên:** thi_thanh_dat
- **Lớp:** cntt2
- **Link repository:**
- **Hệ điều hành (Windows/macOS):** window

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
gci -force
mv .\quy_trinh_thu_am.txt .\docs\
mkdir backup
cp .\data\lich_thu_thang_8.xlsx .\backup\
rm *.tmp
cd .\logs\
ls -Force
Get-ChildItem -Recurse -Force
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
C:\Users\admin\Downloads\starter-kit (1)\starter-kit\phong-thu-am-website
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   1:35 PM                data
d-----        11/11/2026   1:33 PM                docs
d-----        11/11/2026   1:34 PM                evidence
d-----        11/11/2026   1:35 PM                logs
d-----        11/11/2026   1:30 PM                web
------         11/3/2026   7:08 AM             74 .env
-a----         11/3/2026   7:08 AM           2409 bai_lam.md
-a----         11/3/2026   7:08 AM            157 quy_trinh_thu_am.txt
------         11/3/2026   7:08 AM             22 temp_808.tmp

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   1:40 PM                backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:08 AM            992 studio.log



Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:08 AM            992 studio.log


```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
Select-string "status=500" .\logs\studio.log > logs\loi_500.txt
Get-content .\logs\loi_500.txt
```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
logs\studio.log:8:2026-08-28 08:25:34 POST /api/dat-lich status=500
logs\studio.log:11:2026-08-28 08:34:07 POST /api/thanh-toan status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
(Get-content .\logs\studio.log | Select-string "404").Count

```

```text
4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
@`
# Script: tong_hop.ps1
# Tac gia: thi_thanh_dat
# Ngay tao: 11-11-2026
Write-Host "Dang tao bao cao..."
"=== BAO CAO SU CO WEBSITE ===" > .\logs\tong_hop.txt
Get-content .\logs\studio.log | Select-string "status=404" >> .\logs\tong_hop.txt
Get-content .\logs\studio.log | select-string "st=500" >> Measure-Object >> .\logs\tong_hop.txt
Write-Host "Hoan Thanh!"
`@


```

### Nội dung file logs/tong_hop.txt

```text
(Dán nội dung file vào đây – xoá dòng này)

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** 
- Hệ điều hành: Windows 11 64-bit, sử dụng Git Bash (phiên bản 2.44.0).
- Thao tác thực hiện: Chạy lệnh `git pull origin main` tại thư mục dự án trước khi đẩy (push) bài tập lên GitHub.


- **Expected:** 
- Git mở và cập nhật được tệp `.git/FETCH_HEAD`, đồng bộ nhánh `main` thành công để cho phép đẩy code mới lên kho lưu trữ.
- **Actual:** 
- Lệnh bị dừng ngay lập tức và báo lỗi từ chối quyền mở tệp `.git/FETCH_HEAD`.
- **Log:** 
- Log lỗi văn bản:
  $ git pull origin main
  error: open(".git/FETCH_HEAD"): Permission denied
  fatal: Cannot open .git/FETCH_HEAD
- Các cách em đã thử:
  (1) Đã đóng toàn bộ cửa sổ VS Code và mở lại Git Bash bằng quyền "Run as Administrator" (như ảnh chụp màn hình em đính kèm bên dưới).
  (2) Đã kiểm tra phần Properties của thư mục `.git` để bỏ chọn Read-only nhưng tệp FETCH_HEAD vẫn báo khóa quyền truy cập.
### Câu tìm kiếm Google

```text
"Nhập môn Công nghệ Thông tin" filetype:pdf site:ptit.edu.vn -site:123docz.net -site:tailieu.vn

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/lich_thu_thang_8.xlsx`, không cần ghi vào đây.
