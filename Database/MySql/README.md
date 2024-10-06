
# 🗄️ Tất Tần Tật Câu Lệnh Trong MySQL

MySQL là hệ quản trị cơ sở dữ liệu quan hệ (RDBMS) phổ biến nhất hiện nay, được sử dụng rộng rãi trong phát triển web và các ứng dụng doanh nghiệp. Dưới đây là danh sách chi tiết các câu lệnh MySQL phân loại theo từng nhóm chức năng, kèm theo mô tả và ví dụ minh họa.

---

## 📚 Nội Dung

1. [Kết Nối và Quản Lý Cơ Sở Dữ Liệu](#1-kết-nối-và-quản-lý-cơ-sở-dữ-liệu)
2. [Data Definition Language (DDL)](#2-data-definition-language-ddl)
3. [Data Manipulation Language (DML)](#3-data-manipulation-language-dml)
4. [Data Query Language (DQL)](#4-data-query-language-dql)
5. [Data Control Language (DCL)](#5-data-control-language-dcl)
6. [Transaction Control Statements](#6-transaction-control-statements)
7. [Các Câu Lệnh Khác](#7-các-câu-lệnh-khác)

---

## 1. 🖥️ Kết Nối và Quản Lý Cơ Sở Dữ Liệu

### Kết Nối đến MySQL Server

```sql
mysql -u [username] -p
```

- **`-u [username]`**: Tên người dùng MySQL.
- **`-p`**: Yêu cầu nhập mật khẩu.

### Liệt Kê Các Cơ Sở Dữ Liệu

```sql
SHOW DATABASES;
```

### Chọn Cơ Sở Dữ Liệu

```sql
USE [database_name];
```

### Tạo Cơ Sở Dữ Liệu Mới

```sql
CREATE DATABASE [database_name];
```

### Xóa Cơ Sở Dữ Liệu

```sql
DROP DATABASE [database_name];
```

---

## 2. 🏗️ Data Definition Language (DDL)

### Tạo Bảng Mới

```sql
CREATE TABLE [table_name] (
    column1 datatype constraints,
    column2 datatype constraints,
    ...
);
```

**Ví dụ:**

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY AUTO_INCREMENT,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    BirthDate DATE,
    Email VARCHAR(100) UNIQUE
);
```

### Xóa Bảng

```sql
DROP TABLE [table_name];
```

### Thay Đổi Cấu Trúc Bảng

- **Thêm Cột**

  ```sql
  ALTER TABLE [table_name] ADD [column_name] datatype;
  ```

  **Ví dụ:**

  ```sql
  ALTER TABLE Employees ADD Salary DECIMAL(10,2);
  ```

- **Xóa Cột**

  ```sql
  ALTER TABLE [table_name] DROP COLUMN [column_name];
  ```

---

## 3. 🛠️ Data Manipulation Language (DML)

### Chèn Dữ Liệu Vào Bảng

```sql
INSERT INTO [table_name] (column1, column2, ...) VALUES (value1, value2, ...);
```

**Ví dụ:**

```sql
INSERT INTO Employees (FirstName, LastName, BirthDate, Email) 
VALUES ('John', 'Doe', '1985-06-15', 'john.doe@example.com');
```

### Cập Nhật Dữ Liệu

```sql
UPDATE [table_name] SET column1 = value1, column2 = value2, ... WHERE condition;
```

**Ví dụ:**

```sql
UPDATE Employees SET Salary = 60000 WHERE EmployeeID = 1;
```

### Xóa Dữ Liệu

```sql
DELETE FROM [table_name] WHERE condition;
```

**Ví dụ:**

```sql
DELETE FROM Employees WHERE EmployeeID = 1;
```

---

## 4. 🔍 Data Query Language (DQL)

### Chọn Dữ Liệu

```sql
SELECT column1, column2, ... FROM [table_name];
```

- **Chọn tất cả các cột:**

  ```sql
  SELECT * FROM [table_name];
  ```

**Ví dụ:**

```sql
SELECT FirstName, LastName FROM Employees;
```

### Điều Kiện Trong Truy Vấn

```sql
SELECT * FROM Employees WHERE Salary > 50000;
```

### Sắp Xếp Kết Quả

```sql
SELECT * FROM Employees ORDER BY LastName ASC;
```

---

## 5. 🔒 Data Control Language (DCL)

### Cấp Quyền

```sql
GRANT [privileges] ON [database].[table] TO '[username]'@'[host]';
```

**Ví dụ:**

```sql
GRANT SELECT, INSERT ON Employees TO 'john_doe'@'localhost';
```

---

## 6. 🔄 Transaction Control Statements

### Bắt Đầu Giao Dịch

```sql
START TRANSACTION;
```

### Commit Giao Dịch

```sql
COMMIT;
```

### Rollback Giao Dịch

```sql
ROLLBACK;
```

---

## 7. 🧩 Các Câu Lệnh Khác

### Tạo Người Dùng Mới

```sql
CREATE USER 'username'@'host' IDENTIFIED BY 'password';
```

### Xóa Người Dùng

```sql
DROP USER 'username'@'host';
```

---

### Hiển Thị Các Bảng Trong Cơ Sở Dữ Liệu

```sql
SHOW TABLES;
```

---

📝 **Created by ducanhduocdochu**
