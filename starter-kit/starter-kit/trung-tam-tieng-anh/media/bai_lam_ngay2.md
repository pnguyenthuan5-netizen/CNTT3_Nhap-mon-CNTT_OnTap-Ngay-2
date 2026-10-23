# BÀI LÀM – ÔN TẬP NGÀY 2

- **Trần Minh Quân**
- **Lớp:CNTT3**
- **Link repository:**
- **Hệ điều hành Windows:**

## Bài 1. Lọc log thủ công

### Lệnh đã chạy

```shell
PS C:\Users\admin\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh> gc .\logs\access.log | Select-String "ERROR" > logs/error_report.txt
PS C:\Users\admin\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh> gc .\logs\error_report.txt

```

### 2 dòng lỗi đầu tiên trong error_report.txt

```text
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)

```

## Bài 2. Đếm bằng pipeline

### Lệnh

```shell
PS C:\Users\admin\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh> (gc .\logs\access.log | Select-String "Warning").count
PS C:\Users\admin\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh> (gc .\logs\payment.log | Select-String "ERROR").count

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
WARNING trong access.log:4
ERROR trong payment.log:3
```

## Bài 3. Chạy script auto_warning (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
#PS C:\Users\admin\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh> .\auto_warning.ps1

```

### Nội dung file logs/warning_report.txt

```text
2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi


```

## Bài 4. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
PS C:\Users\admin\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh> .\AUTOWARNING.ps1
Dang loc canh bao thanh toan..."
=== TONG HOP ACCESS LOG ===
Hoan thanh!

```

### Nội dung file logs/tong_hop_ngay2.txt

```text
5

2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:33:51 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:37:19 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:49:43 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:53:11 [ERROR] Het thoi gian cho (timeout)


```

## Bài 5. Câu hỏi ngắn

- **a) lệnh > là lệnh đè sẽ khiến mất dữ liệu cũ khi chèn thêm dữ liệu mới còn lệnh >> là nối tiếp dữ liệu mới và dữ liệu cũ**
- **b)khi sử dụng dấu > thì dữ liệu cũ sẽ mất và chỉ hiển thị nội dung mới khi lệnh chạy**
- **c) vì đường dẫn trên mỗi máy tính của mỗi người là khác nhau nên sử dụng đường dẫn tương đối sẽ tránh gãy đường dẫn và tính bảo mật cao**

## Tự chấm (điền sau khi có đáp án)

- **Điểm tự chấm:** ..../100
- **Lỗi mình đã mắc và cách sửa:**
