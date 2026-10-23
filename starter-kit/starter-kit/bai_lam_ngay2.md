


# BÀI LÀM – ÔN TẬP NGÀY 2

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#b%C3%A0i-l%C3%A0m--%C3%B4n-t%E1%BA%ADp-ng%C3%A0y-2)

-   **Họ tên:** Nguyễn Thuận Phát
-   **Lớp:** HNKS26CNTT3
-   **Link repository:** 
-   **Hệ điều hành (Windows/macOS):** Windows

## Bài 1. Lọc log thủ công

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#b%C3%A0i-1-l%E1%BB%8Dc-log-th%E1%BB%A7-c%C3%B4ng)

### Lệnh đã chạy

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#l%E1%BB%87nh-%C4%91%C3%A3-ch%E1%BA%A1y)

cat .\logs\access.log | select-string "ERROR" > .\logs\error_report.txt
cat .\logs\error_report.txt

### 2 dòng lỗi đầu tiên trong error_report.txt

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#2-d%C3%B2ng-l%E1%BB%97i-%C4%91%E1%BA%A7u-ti%C3%AAn-trong-error_reporttxt)

```
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)

```

## Bài 2. Đếm bằng pipeline

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#b%C3%A0i-2-%C4%91%E1%BA%BFm-b%E1%BA%B1ng-pipeline)

### Lệnh

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#l%E1%BB%87nh)

(cat .\logs\access.log | select-string "WARNING").count
(cat .\logs\payment.log | select-string "ERROR").count

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#k%E1%BA%BFt-qu%E1%BA%A3-%C4%91%E1%BA%BFm-windows-gi%C3%A1-tr%E1%BB%8B-count-macos-con-s%E1%BB%91-in-ra)

```
WARNING trong access.log: 4
ERROR trong payment.log: 3

```

## Bài 3. Chạy script auto_warning (.ps1 hoặc .sh)

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#b%C3%A0i-3-ch%E1%BA%A1y-script-auto_warning-ps1-ho%E1%BA%B7c-sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#l%E1%BB%87nh-ch%E1%BA%A1y-windows-n%E1%BA%BFu-d%C3%B9ng-ph%E1%BB%A5-l%E1%BB%A5c-2-th%C3%AC-ghi-c%E1%BA%A3-2-l%E1%BB%87nh)

.\auto_warning.ps1

### Nội dung file logs/warning_report.txt

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#n%E1%BB%99i-dung-file-logswarning_reporttxt)

```
=== CANH BAO THANH TOAN ===

2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi

```

## Bài 4. Báo cáo tổng hợp

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#b%C3%A0i-4-b%C3%A1o-c%C3%A1o-t%E1%BB%95ng-h%E1%BB%A3p)

### Các lệnh đã chạy

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#c%C3%A1c-l%E1%BB%87nh-%C4%91%C3%A3-ch%E1%BA%A1y)

new-item .\logs\tong_hop_ngay_2.txt
"=== TONG HOP ACCESS LOG ===" > .\logs\tong_hop_ngay_2.txt
cat .\logs\access.log | Select-String "ERROR" >> .\logs\tong_hop_ngay_2.txt
cat .\logs\payment.log | Select-String "WARNING" >> .\logs\tong_hop_ngay_2.txt

### Nội dung file logs/tong_hop_ngay2.txt

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#n%E1%BB%99i-dung-file-logstong_hop_ngay2txt)

```
=== TONG HOP ACCESS LOG ===

2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:33:51 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:37:19 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:49:43 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:53:11 [ERROR] Het thoi gian cho (timeout)



2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi

```

## Bài 5. Câu hỏi ngắn

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#b%C3%A0i-5-c%C3%A2u-h%E1%BB%8Fi-ng%E1%BA%AFn)

-   **a)** Lệnh > và >> khác nhau:

">" là ghi đè nội dung vào file, có nghĩa là nếu trong file đó đã có nội dung gì thì sẽ bị xóa sạch đi để thay thế bằng nội dung mới sau ">" vào file đó

Còn ">>" là nối tiếp, có nghĩa file đó nếu có nội dung gì thì sẽ được enter xuống 1 dòng rồi ghi tiếp nội dung sau ">>" vào file đó

-   **b)** Nếu dùng > thay cho >> thì nội dung trong file tong_hop_ngay_2.txt sẽ thay đổi như sau:

Mất dòng "=== TONG HOP ACCESS LOG ===", nội dung các dòng chứa "ERROR" vẫn được in ra bình thường

-   **c)** Bởi vì nếu sử dụng đường dẫn tuyệt đối sẽ bị lộ thông tin cá nhân, đồng thời khi chuyển file sang máy khác thì sẽ bị lỗi không tìm thấy đường dẫn

## Tự chấm (điền sau khi có đáp án)

[](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_Nhap-mon-CNTT_OnTap-Ngay2/blob/main/bai_lam_ngay2.md#t%E1%BB%B1-ch%E1%BA%A5m-%C4%91i%E1%BB%81n-sau-khi-c%C3%B3-%C4%91%C3%A1p-%C3%A1n)

-   **Điểm tự chấm:** 100/100
-   **Lỗi mình đã mắc và cách sửa:** Không có lỗi