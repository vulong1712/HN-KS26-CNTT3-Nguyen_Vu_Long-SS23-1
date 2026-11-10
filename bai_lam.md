# BÀI LÀM – (ĐỀ LUYỆN TẬP SỐ 02)

- **Mã đề:** 02
- **Họ tên:** Nguyễn Vũ Long
- **Lớp:** HN-KS26-CNTT3
- **Link repository:** [GitHub](https://github.com/vulong1712/HN-KS26-CNTT3-Nguyen_Vu_Long-SS22-Test)
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Force
mv .\bien_ban_ban_giao.txt .\docs\
mkdir backup
cp .\data\ban_ve_thang_11.xlsx .\backup\
rm .\cache_991.tmp
cd .\logs\
ls
cd..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
  Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\Luyen_Tap_11_9\starter-kit\rap-phim-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         9/11/2026   3:43 PM                backup
d-----         9/11/2026   3:41 PM                data
d-----         9/11/2026   3:42 PM                docs
d-----         9/11/2026   3:40 PM                evidence
d-----         9/11/2026   3:41 PM                logs
d-----         9/11/2026   3:07 PM                web
-a----         9/11/2026   3:07 PM             82 .env
-a----         9/11/2026   3:07 PM           2611 bai_lam.md


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\Luyen_Tap_11_9\starter-kit\rap-phim-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         9/11/2026   3:07 PM           5693 ban_ve_thang_11.xlsx


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\Luyen_Tap_11_9\starter-kit\rap-phim-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         9/11/2026   3:07 PM           5693 ban_ve_thang_11.xlsx


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\Luyen_Tap_11_9\starter-kit\rap-phim-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         9/11/2026   3:07 PM            172 bien_ban_ban_giao.txt


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\Luyen_Tap_11_9\starter-kit\rap-phim-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         9/11/2026   3:07 PM            893 server.log


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\Luyen_Tap_11_9\starter-kit\rap-phim-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         9/11/2026   3:07 PM                images
-a----         9/11/2026   3:20 PM            620 app.js
-a----         9/11/2026   3:19 PM            589 index.html
-a----         9/11/2026   3:07 PM            460 style.css


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\Luyen_Tap_11_9\starter-kit\rap-phim-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         9/11/2026   3:07 PM            342 logo-cinebox.png
```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng ERROR

```shell
Get-Content .\logs\server.log | Select-String "ERROR">.\logs\loi_error.txt

```

### 2 dòng đầu tiên trong logs/loi_error.txt

```text
2026-11-01 09:25:40 ERROR POST /api/mua-ve
2026-11-01 09:29:11 ERROR POST /api/thanh-toan-qr

```

### b) Lệnh đếm số dòng WARNING và kết quả

```shell
(Get-Content .\logs\server.log | Select-String "WARNING").Count   

```

```text
5

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===

2026-11-01 09:08:10 WARNING GET /phim-sap-chieu-cu
2026-11-01 09:15:30 WARNING GET /uu-dai-thang-9
2026-11-01 09:36:50 WARNING GET /images/phong-imax.jpg
2026-11-01 10:01:20 WARNING GET /voucher-het-han
2026-11-01 10:12:55 WARNING GET /combo-bap-nuoc


6


```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [X] README.md: Heading 1, mô tả có **in đậm** và _in nghiêng_, bảng, code block, task list, blockquote
- [X] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [X] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | -------------------------- | --------------------------- | -------------- |
| 1 | Console | app.js:18 Uncaught ReferenceError: hienThiBangGia is not defined (anonymous) @ app.js:18 | Sửa lại đường dẫn file trong index.html |
| 2 | Network | Không tìm thấy file ảnh | Sửa lại trongg index.html |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Không hiện hình ảnh logo và bảng dữ liệu trong index.html
- **Expected:** Sửa được lỗi, Developer Tools không báo lỗi
- **Actual:** Lỗi chưa được sửa, file logo hiện hình ảnh lỗi và không hiển thị bảng dữ liệu trên web
- **Log:**  app.js:18 Uncaught ReferenceError: hienThiBangGia is not defined (anonymous) @ app.js:18

### Câu tìm kiếm Google

```text
site:stackoverflow.com "ERR_FILE_NOT_FOUND"
```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/ban_ve_thang_11.xlsx`, không cần ghi vào đây.
