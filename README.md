# THIẾT KẾ CƠ SỞ DỮ LIỆU QUẢN LÝ CỬA TIỆM GIẶT SẤY

**Dự án nhóm | SQL Server | Database Design | Data Management**

## 1. Giới thiệu dự án

Dự án tập trung thiết kế và xây dựng cơ sở dữ liệu quan hệ phục vụ hoạt động quản lý cửa tiệm giặt sấy.

Hệ thống được thiết kế nhằm quản lý thông tin khách hàng, đơn hàng, dịch vụ, máy giặt sấy, nhân viên, lịch làm việc và thanh toán.

Ngoài ra, dự án xây dựng các truy vấn SQL phục vụ tổng hợp dữ liệu, theo dõi hoạt động kinh doanh và đánh giá hiệu suất vận hành.

**Mục tiêu dự án:**
- Phân tích yêu cầu nghiệp vụ của cửa tiệm giặt sấy.
- Thiết kế sơ đồ quan hệ thực thể (ERD).
- Xây dựng cơ sở dữ liệu quan hệ.
- Thiết lập khóa chính, khóa ngoại và các ràng buộc dữ liệu.
- Xây dựng truy vấn hỗ trợ quản lý và báo cáo kinh doanh.

## 2. Công nghệ sử dụng

| Công nghệ | Mục đích |
|---|---|
| SQL Server | Hệ quản trị cơ sở dữ liệu |
| SQL | Tạo bảng, quản lý và truy vấn dữ liệu |
| ERD | Thiết kế mô hình quan hệ thực thể |
| Database Normalization | Chuẩn hóa cấu trúc dữ liệu |

## 3. Thiết kế cơ sở dữ liệu

Hệ thống được thiết kế gồm 12 bảng dữ liệu.

| Bảng | Chức năng |
|---|---|
| CUSTOMER | Quản lý thông tin khách hàng |
| SERVICE | Quản lý dịch vụ và đơn giá |
| MACHINE | Quản lý thông tin máy giặt sấy |
| CUSTOMERORDER | Quản lý đơn hàng |
| PACKAGE | Quản lý các phần đồ được tách từ đơn hàng |
| STAFF | Quản lý nhân viên |
| SHIFT | Quản lý ca làm việc |
| WORKSCHEDULE | Quản lý lịch làm việc |
| PACKHANDLING | Ghi nhận các thao tác xử lý đồ giặt |
| ORDERHANDLING | Ghi nhận quá trình tiếp nhận và bàn giao đơn hàng |
| PAYMENT | Quản lý thanh toán |
| PAYMENTDETAIL | Quản lý chi tiết thanh toán theo đơn hàng |

### Mô hình dữ liệu

Cơ sở dữ liệu sử dụng các mối quan hệ một-nhiều và quan hệ thông qua bảng trung gian để liên kết thông tin khách hàng, đơn hàng, nhân viên và thanh toán.

Các bảng được thiết kế với khóa chính (Primary Key), khóa ngoại (Foreign Key) và ràng buộc kiểm tra (CHECK Constraint).

## 4. Quy trình thực hiện

### Bước 1: Phân tích yêu cầu nghiệp vụ

Phân tích các hoạt động chính của cửa tiệm:

- Tiếp nhận yêu cầu giặt sấy.
- Phân chia đồ giặt theo khối lượng và loại dịch vụ.
- Phân công máy giặt sấy.
- Theo dõi quá trình xử lý đơn hàng.
- Quản lý ca làm việc của nhân viên.
- Ghi nhận thanh toán.

### Bước 2: Thiết kế sơ đồ ERD

- Xác định các thực thể và thuộc tính.
- Phân tích mối quan hệ giữa các thực thể.
- Xác định khóa chính và khóa ngoại.
- Xây dựng sơ đồ quan hệ thực thể.

### Bước 3: Chuẩn hóa dữ liệu

Thiết kế lược đồ quan hệ và phân tích các phụ thuộc dữ liệu.

Theo báo cáo đồ án, nhóm xây dựng các quan hệ đáp ứng dạng chuẩn thứ ba (3NF) nhằm hạn chế dư thừa dữ liệu và bất thường khi cập nhật.

### Bước 4: Xây dựng cơ sở dữ liệu

Sử dụng SQL Server để:

- Tạo cơ sở dữ liệu LAUNDRY.
- Tạo 12 bảng dữ liệu.
- Thiết lập các ràng buộc khóa chính, khóa ngoại.
- Quy định kiểu dữ liệu cho từng thuộc tính.
- Sử dụng CHECK Constraint để kiểm soát tính hợp lệ của dữ liệu.

### Bước 5: Xây dựng truy vấn SQL

Thực hiện các thao tác cơ bản:

- INSERT: Thêm dữ liệu.
- UPDATE: Cập nhật dữ liệu.
- DELETE: Xóa dữ liệu.
- SELECT: Truy xuất dữ liệu.

## 5. Các truy vấn báo cáo kinh doanh

### 5.1. Báo cáo doanh thu

- Tổng hợp doanh thu theo tháng.
- Phân tích doanh thu theo từng loại dịch vụ.

### 5.2. Báo cáo hiệu suất nhân viên

- Thống kê số lượng đơn hàng từng nhân viên xử lý.
- Tổng hợp khối lượng đồ giặt do nhân viên xử lý.

### 5.3. Báo cáo hiệu suất máy giặt

- Thống kê số lượng lượt xử lý của từng máy.
- Tổng hợp khối lượng đồ giặt theo máy.

### 5.4. Phân tích khách hàng

- Thống kê số lượng đơn hàng theo khách hàng.
- Xác định khách hàng có tần suất sử dụng dịch vụ cao.

### 5.5. Theo dõi đơn hàng

- Truy vấn trạng thái đơn hàng.
- Tổng hợp số lượng đơn hàng theo dịch vụ và trạng thái.

## 6. Kỹ năng thể hiện qua dự án

- Phân tích yêu cầu nghiệp vụ.
- Thiết kế cơ sở dữ liệu quan hệ.
- Xây dựng sơ đồ ERD.
- Chuẩn hóa dữ liệu.
- Xây dựng bảng và thiết lập ràng buộc.
- Viết truy vấn SQL và JOIN nhiều bảng.
- Tổng hợp dữ liệu phục vụ báo cáo kinh doanh.
- Phối hợp thực hiện dự án nhóm.

## 7. Mã nguồn

Mã nguồn SQL được cung cấp trong file:

`Nhom3_241BIE300405.sql`

**Lưu ý:** File sao lưu cơ sở dữ liệu (.bak) không được công khai trong repository này.

## 8. Thông tin dự án

- **Hình thức:** Dự án nhóm – 4 thành viên.
- **Học phần:** Cơ sở dữ liệu.
- **Trường:** Đại học Kinh tế – Luật, ĐHQG TP.HCM.
- **Thời gian:** 11/2024.

---

*Dự án được thực hiện phục vụ mục đích học tập và nghiên cứu.*
