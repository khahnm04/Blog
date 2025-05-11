## 1. SQL Là Gì? Tại Sao Nên Học SQL?

SQL là ngôn ngữ được sử dụng để quản lý và thao tác dữ liệu trong các cơ sở dữ liệu quan hệ (Relational Database). Từ việc tạo bảng, thêm dữ liệu, truy vấn thông tin, đến phân tích dữ liệu phức tạp, SQL là công cụ không thể thiếu trong lĩnh vực công nghệ thông tin, phân tích dữ liệu, và khoa học dữ liệu.

**Lý do bạn nên học SQL:**
- Dễ học, cú pháp rõ ràng.
- Được sử dụng rộng rãi trong các công ty công nghệ (Google, Amazon, Meta...).
- Giúp bạn làm việc hiệu quả với dữ liệu lớn.

---

## 2. Tạo và Quản Lý Cơ Sở Dữ liệu

### Tạo Database
Để bắt đầu, bạn cần tạo một **database** (cơ sở dữ liệu) để lưu trữ dữ liệu. Câu lệnh `CREATE DATABASE` sẽ giúp bạn làm điều này:

```sql
CREATE DATABASE DEMO;
```

Sau khi tạo, sử dụng `USE DEMO;` để chọn database mà bạn muốn thao tác.

### Tạo Table
Table (bảng) là nơi lưu trữ dữ liệu theo hàng (row) và cột (column). Mỗi cột đại diện cho một thuộc tính, còn mỗi hàng là một bản ghi.

Ví dụ, tạo bảng `Student` để lưu thông tin sinh viên:

```sql
CREATE TABLE Student (
    id VARCHAR(20) NOT NULL, -- Mã sinh viên, không được để trống
    lop VARCHAR(50), -- Lớp
    ten VARCHAR(50), -- Tên
    gpa FLOAT, -- Điểm trung bình
    PRIMARY KEY (id) -- Khóa chính
);
```

**Một số kiểu dữ liệu phổ biến:**
- **Số nguyên**: `INT`, `BIGINT`
- **Số thực**: `FLOAT`, `DOUBLE`, `DECIMAL`
- **Chuỗi**: `CHAR`, `VARCHAR`
- **Ngày giờ**: `DATE`, `TIME`

### Xóa Database hoặc Table
Nếu muốn xóa database hoặc table, bạn có thể sử dụng:

```sql
DROP DATABASE DEMO; -- Xóa database
DROP TABLE Student; -- Xóa table
```

---

## 3. Thêm Dữ liệu Vào Bảng

Để thêm dữ liệu, sử dụng câu lệnh `INSERT INTO`. Ví dụ, thêm thông tin sinh viên vào bảng `Student`:

```sql
INSERT INTO Student VALUES
('001', 'CNTT1', 'Nguyen Van Nam', 2.8),
('002', 'CNTT2', 'Pham Van Long', 3.2),
('003', 'CNTT1', 'Huynh Van Phuoc', 2.1),
('004', 'CNTT2', 'Pham Thi Hang', 2.6);
```

Nếu chỉ muốn thêm dữ liệu vào một số cột, bạn có thể chỉ định cột:

```sql
INSERT INTO Student (id, ten) VALUES ('005', 'Le Thi Mai');
```

**Lưu ý khi thêm dữ liệu kiểu `DATE`:**
Sử dụng định dạng `YYYY-MM-DD`. Ví dụ:

```sql
INSERT INTO Customer VALUES
('CUS01', 'Dang Phuong Nam', 'Thanh Oai, Ha Noi', '1999-01-01');
```

---

## 4. Truy Vấn Dữ liệu

### Truy Vấn Cơ Bản
Sử dụng `SELECT` để lấy dữ liệu từ bảng. Ví dụ, lấy tất cả thông tin sinh viên:

```sql
SELECT * FROM Student;
```

Nếu chỉ muốn lấy một số cột:

```sql
SELECT id, ten FROM Student;
```

### Đặt Bí Danh (Alias)
Để làm cho kết quả dễ đọc hơn, bạn có thể sử dụng `AS` để đặt bí danh cho cột:

```sql
SELECT id AS MaSV, ten AS HoTen, gpa AS Diem FROM Student;
```

### Lọc Dữ liệu Với `WHERE`
Câu lệnh `WHERE` giúp lọc dữ liệu theo điều kiện. Ví dụ, lấy sinh viên có GPA >= 2.8:

```sql
SELECT * FROM Student WHERE gpa >= 2.8;
```

Kết hợp nhiều điều kiện:

```sql
SELECT * FROM Student WHERE lop = 'CNTT2' AND gpa >= 2.5;
```

Sử dụng `BETWEEN` để lọc trong khoảng:

```sql
SELECT * FROM Student WHERE gpa BETWEEN 2.1 AND 2.9;
```

Sử dụng `IN` để lọc giá trị trong danh sách:

```sql
SELECT * FROM Student WHERE lop IN ('CNTT1', 'CNTT2');
```

### Sử Dụng `LIKE` Để Tìm Kiếm Chuỗi
`LIKE` rất hữu ích khi tìm kiếm chuỗi. Một số ví dụ:

- Tên bắt đầu bằng "Hu":

```sql
SELECT * FROM Customer WHERE CustomerName LIKE 'Hu%';
```

- Tên kết thúc bằng "ore":

```sql
SELECT * FROM Customer WHERE CustomerName LIKE '%ore';
```

- Tên có ký tự thứ 3 là "a":

```sql
SELECT * FROM Customer WHERE CustomerName LIKE '__a%';
```

---

## 5. Các Hàm Hữu Ích Trong SQL

SQL cung cấp nhiều hàm tích hợp để xử lý dữ liệu:

### Hàm Xử Lý Chuỗi
- `LENGTH`: Đếm độ dài chuỗi.
- `LEFT`, `RIGHT`: Lấy n ký tự từ trái/phải.
- `SUBSTR`: Cắt chuỗi từ vị trí a, lấy b ký tự.
- `TRIM`, `UPPER`, `LOWER`: Xử lý chuỗi (xóa khoảng trắng, chuyển đổi chữ hoa/thường).

Ví dụ:

```sql
SELECT * FROM Customer WHERE LENGTH(CustomerName) >= 25;
SELECT * FROM Customer WHERE LEFT(CustomerName, 3) = 'Hun';
```

### Hàm Xử Lý Ngày Giờ
- `YEAR`, `MONTH`, `DAY`: Lấy năm, tháng, ngày.
- `DATE`: Lấy ngày đầy đủ.

Ví dụ:

```sql
SELECT * FROM Orders WHERE YEAR(OrderDate) = 1996 AND MONTH(OrderDate) = 11;
```

### Hàm Tính Toán
- `MIN`, `MAX`: Tìm giá trị nhỏ nhất/lớn nhất.
- `COUNT`: Đếm số bản ghi.
- `AVG`, `SUM`: Tính trung bình/tổng.

Ví dụ:

```sql
SELECT MIN(price) FROM Products;
SELECT COUNT(Country) FROM Customers WHERE Country = 'Brazil';
```

---

## 6. Sắp Xếp và Gom Nhóm

### Sắp Xếp Với `ORDER BY`
Sử dụng `ORDER BY` để sắp xếp kết quả:

```sql
SELECT * FROM Customers ORDER BY Country; -- Sắp xếp theo quốc gia tăng dần
SELECT * FROM Customers ORDER BY Country DESC; -- Giảm dần
```

Sắp xếp theo nhiều cột:

```sql
SELECT * FROM Customers ORDER BY Country, City DESC;
```

### Gom Nhóm Với `GROUP BY`
`GROUP BY` giúp gom các bản ghi có cùng giá trị vào một nhóm và áp dụng hàm tính toán. Ví dụ, đếm số khách hàng theo quốc gia:

```sql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;
```

Kết hợp với `HAVING` để lọc nhóm:

```sql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) >= 5;
```

---

## 7. Kết Hợp Bảng Với `JOIN`

Khi làm việc với nhiều bảng, bạn cần sử dụng `JOIN` để kết hợp dữ liệu:

- **INNER JOIN**: Chỉ trả về các bản ghi khớp nhau ở cả hai bảng.
- **LEFT JOIN**: Trả về tất cả bản ghi từ bảng trái, kể cả không khớp.
- **RIGHT JOIN**: Trả về tất cả bản ghi từ bảng phải.
- **CROSS JOIN**: Kết hợp tất cả bản ghi từ cả hai bảng.

Ví dụ, truy vấn các đơn hàng và thông tin nhân viên xử lý:

```sql
SELECT *
FROM Employees
INNER JOIN Orders
ON Employees.EmployeeID = Orders.EmployeeID;
```

---

## 8. Thứ Tự Thực Thi Câu Lệnh SQL

Hiểu thứ tự thực thi câu lệnh SQL giúp bạn viết truy vấn hiệu quả hơn:

1. **FROM** và **JOIN**: Xác định bảng và mối quan hệ.
2. **WHERE**: Lọc dữ liệu.
3. **GROUP BY**: Gom nhóm.
4. **HAVING**: Lọc nhóm.
5. **SELECT**: Chọn cột.
6. **ORDER BY**: Sắp xếp kết quả.

---

## 9. Mẹo Học SQL Hiệu Quả

- **Thực hành thường xuyên**: Sử dụng các nền tảng như MySQL Workbench, SQL Fiddle, hoặc LeetCode để luyện tập.
- **Hiểu dữ liệu**: Trước khi viết truy vấn, hãy hiểu rõ cấu trúc bảng và mối quan hệ giữa chúng.
- **Tối ưu truy vấn**: Tránh sử dụng `SELECT *` trong sản phẩm thực tế, chỉ chọn cột cần thiết để tăng hiệu suất.
- **Đọc tài liệu**: Tham khảo tài liệu chính thức của MySQL (https://dev.mysql.com/doc/) hoặc các nguồn như W3Schools.

---

## 10. Kết Luận

SQL không chỉ là một ngôn ngữ lập trình, mà còn là chìa khóa mở ra thế giới dữ liệu. Từ việc tạo cơ sở dữ liệu, thêm dữ liệu, truy vấn, đến phân tích phức tạp, SQL giúp bạn làm chủ thông tin một cách dễ dàng. Hy vọng bài viết này đã cung cấp cho bạn một cái nhìn tổng quan và cảm hứng để tiếp tục hành trình học SQL!
