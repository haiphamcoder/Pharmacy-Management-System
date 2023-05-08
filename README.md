# Thiết kế hệ thống hướng đối tượng cho bài toán xây dựng phần mềm quản lý cửa hàng bán dược phẩm sử dụng CSharp, WPF và MySQL

## I. Mục tiêu và yêu cầu của hệ thống

Phần mềm quản lý cửa hàng bán dược phẩm cần đáp ứng các yêu cầu sau:

1. Quản lý thông tin sản phẩm, nhà cung cấp, khách hàng.
2. Quản lý nhập hàng, xuất hàng, tồn kho.
3. Quản lý doanh thu, chi phí, lợi nhuận.
4. Quản lý thông tin nhân viên, phân quyền sử dụng phần mềm.
5. Báo cáo thống kê, xuất báo cáo.

## II. Phân tích và thiết kế hệ thống hướng đối tượng

1. Xác định các đối tượng (class) chính:
- Sản phẩm (Product)
- Nhà cung cấp (Supplier)
- Khách hàng (Customer)
- Nhập hàng (Import)
- Xuất hàng (Export)
- Kho hàng (Inventory)
- Doanh thu (Revenue)
- Chi phí (Expense)
- Nhân viên (Employee)
- Phân quyền (Role)
- Báo cáo (Report)

2. Thiết kế các thuộc tính và phương thức cho các đối tượng:

```csharp
class Product
{
    int ProductID;
    string ProductName;
    string Description;
    double Price;
    int Quantity;
    int SupplierID;
    DateTime ExpirationDate;
    
    void AddProduct();
    void UpdateProduct();
    void DeleteProduct();
    List<Product> GetAllProducts();
}
```

```csharp
class Supplier
{
    int SupplierID;
    string SupplierName;
    string Address;
    string PhoneNumber;
    
    void AddSupplier();
    void UpdateSupplier();
    void DeleteSupplier();
    List<Supplier> GetAllSuppliers();
}
```

```csharp
class Customer
{
    int CustomerID;
    string CustomerName;
    string Address;
    string PhoneNumber;
    
    void AddCustomer();
    void UpdateCustomer();
    void DeleteCustomer();
    List<Customer> GetAllCustomers();
}
```

```csharp
class Import
{
    int ImportID;
    int ProductID;
    int SupplierID;
    int Quantity;
    DateTime ImportDate;
    
    void AddImport();
    void UpdateImport();
    void DeleteImport();
    List<Import> GetAllImports();
}
```

```csharp
class Export
{
    int ExportID;
    int ProductID;
    int CustomerID;
    int Quantity;
    DateTime ExportDate;
    
    void AddExport();
    void UpdateExport();
    void DeleteExport();
    List<Export> GetAllExports();
}
```

```csharp
class Inventory
{
    int ProductID;
    int Quantity;
    
    List<Inventory> GetAllInventories();
}
```

```csharp
class Revenue
{
    DateTime Date;
    double TotalRevenue;
    
    double CalculateRevenue();
}
```

```csharp
class Expense
{
    DateTime Date;
    double TotalExpense;
    
    double CalculateExpense();
}
```

```csharp
class Employee
{
    int EmployeeID;
    string EmployeeName;
    string Address;
    string PhoneNumber;
    string Username;
    string Password;
    int RoleID;
    
    void AddEmployee();
    void UpdateEmployee();
    void DeleteEmployee();
    List<Employee> GetAllEmployees();
}
```

```csharp
class Role
{
    int RoleID;
    string RoleName;
    
    void AddRole();
    void UpdateRole();
    void DeleteRole();
    List<Role> GetAllRoles();
}
```

```csharp
class Report
{
    DateTime FromDate;
    DateTime ToDate;
    
    List<Report> GenerateReport();
}
```

3. Thiết kế giao diện người dùng (UI) sử dụng WPF:
- Giao diện đăng nhập
- Giao diện chính (Main Form) với menu chức năng
- Giao diện quản lý sản phẩm, nhà cung cấp, khách hàng, nhập hàng, xuất hàng, tồn kho, doanh thu, chi phí, nhân viên, phân quyền, báo cáo.

## III. Triển khai và kiểm thử hệ thống
1. Cài đặt môi trường phát triển: Visual Studio, MySQL.
2. Tạo cơ sở dữ liệu và thiết lập kết nối giữa ứng dụng và cơ sở dữ liệu.
3. Triển khai mã nguồn cho các đối tượng và giao diện người dùng.
4. Kiểm thử chức năng, đảm bảo hệ thống hoạt động ổn định và đáp ứng yêu cầu.

## IV. Bảo trì và nâng cấp hệ thống
1. Đảm bảo hệ thống hoạt động ổn định, khắc phục các lỗi phát sinh.
2. Nâng cấp hệ thống theo yêu cầu của người dùng, cải tiến chức năng và hiệu năng.