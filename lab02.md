# Phân Tích Ca Sử Dụng: Use case Login

## 1.1 Cơ chế phân tích 
Account: Chứa tài khoản bao gồm name và password

**Cơ chế phân tích:** Security

Dùng Security vì cần bảo mật thông tin của các actor

## 1.2 Phân tích Login
Các lớp phân tích:

* Boundary: Login GUI
* Controller: Login Controller
* Entity: Accounts

Biểu đồ tương tác:

Basic flow:

![Diagram](https://www.planttext.com/api/plantuml/png/R90z3i8m38LtdyBgpWKO4AX22AaRAdj83Qf84nIxGZq6uWISemCBuXwSW2lW_crCoNlVoxELR_jSifWeTUK0-5nwZ849G4fnXCdk_S3NxTFUCGkdqYS0nag8c3D5E8JQ5oOscFGGD_asGSFT2JPuYS6DA1sKezW7iXJ8wuG6LzPgYG1qXJXRT6znZcilAhsfw2-u6EPhY0Lqfh8iLJJi07fNP-nLUszSMHYXATltJMckhINcO-rWIRxGJ_W1003__mC0)

Alternative Flows: 

![Diagram](https://www.planttext.com/api/plantuml/png/R90nZW8n34LxdyAQVY-m1GADq0ffEWIzD-D54S51YKTeZh7Y19o3OXl4FJZ1NW676QYe4l_dF2VvF_zDirBIRXS0yjOBffWPGBq6ncfvFU7bztO-OXCtNYe0SXeJhZ8d-8wTj9Hwh1uGlrQB2YcN5LmKJJ6Cg1wgmEdHqDJ0OXDwd3bd4WKeGloObBFuYNDHAuLs_1RiAUT3J2sKq5XJ6nhk0BQtPFHQlARWMr8UmQ0PUd_81tv9og0diHVM98u3J5bQ-vix0000__y30000)

# Phân Tích Ca Sử Dụng: Maintain Employee Information
## 2.1 Cơ chế phân tích
Employ: Thông tin của 1 nhân viên

**Cơ chế phân tích:** Persistence, Security

Cần cơ chế Persistence vì cần phải lưu trữ dữ liệu của hệ thống

Cần cơ thế Sercurity vì cần bảo mật thông tin cho các nhân viên
## 2.2 Phân tích Maintain Employee Information
Các lớp phân tích: 
* Boundary: EmployeeInformation GUI
* Controller: EmployeeInformation Controller
* Entity: EmployeeInformation
Biểu đồ tương tác:

![Diagram](https://www.planttext.com/api/plantuml/png/b5InRjim4Dtv5GSlMHfqrr0aa9B2GpjKzGVGr2aYJ94gHINGs2bpq2zensv5XmBsaC51_qDVq5_eKJ9aoRBJL80aKdptxjsxW_vi7YzAnwshSiLOkP8Qh2cHCIUTGfZ5lx_2qqEp-GBlkDIERhZA2sLgH9ZhrDYSEsaqdCDb5FL7CyQuSCR2eaJBbgRI2RSrp8w6lbtCPy1B_sR2Q6UDEe4CkrE5jWs8GuQQTDPzNiPyGZX_uyaWW1WL2eS9N2O9S3t0tLXJ5Urd1dHvE4MrqG5ym4yLbWw8dVO31IrsdEAgnHoJEoIEGuA65hd37djMmZnwHHeT5BmM6OeL9AZaBTgwZQKW2ksfWv750yIkripSWSQxFG9rSjAGHP5uBKSywKuENPcOSg1aaERGaxREiHa1N4kTx4jRrfvmN580aImBnUlJveuDekhuBOvbdS77Z1XSrgmVGMVRdpae6cPzGnjUmR9P_w3rquDiDfyhMD7hNaDcclKl0MBxhVBeUvs1bTll15nwW6kPkN9xOTT-mjlF4zl-MGIgSYyQtXlt75ldR2BJ52qrmhls6aAk1QgEZ0AVQtj4Y-DjxqxOOSAuG27JUkJgIthzWbR_HwUzsTE9fDz1Acq-a3wPY5szFI_R6JwTsSx48HSR-7b13_-7_0i00F__0m00)

# Phân Tích Ca Sử Dụng: Maintain Purchase Order
## 3.1 Cơ chế phân tích: 
PurchaseOrder: Quản lý thông tin đơn hàng. Xác minh quyền truy cập (kiểm tra id nhân viên). Cập nhật trạng thái (thêm, sửa, xóa).

**Cơ chế phân tích:** Persistency, Transaction Management, Security
* Persistency: Purchase orders cần được lưu trữ vĩnh viễn để theo dõi thông tin lịch sử và xử lý thanh toán.
* Transaction Management: Quản lý giao dịch khi thêm, sửa, xóa purchase orders nhằm đảm bảo tính toàn vẹn dữ liệu.
* Security: Đảm bảo rằng chỉ nhân viên được phân quyền mới có thể truy cập hoặc chỉnh sửa purchase orders.

Employee

**Cơ chế phân tích:** Persistency, Information Exchange, Transaction Management, Security
* Persistency: Lưu trữ thông tin nhân viên 
* Information Exchange: Trao đổi thông tin với hệ thống khác
* Transaction Management: Giao dịch liên quan đến cập nhật thông tin hoa hồng và xử lý thanh toán cần đảm bảo tính nhất quán.
* Security: Bảo vệ thông tin cá nhân nhân viên, đặc biệt là thông tin thanh toán (tài khoản ngân hàng).

Timecard 

**Cơ chế phân tích:** Persistency, Transaction Management, Process Control and Synchronization
* Persistency: Lưu trữ thời gian làm việc của nhân viên để tính toán lương và quản lý mã charge.
* Transaction Management: Đảm bảo rằng dữ liệu nhập thời gian làm việc không bị ghi đè hoặc xung đột khi cập nhật bởi nhiều nguồn.
* Process Control and Synchronization: Đồng bộ hóa giữa việc ghi nhận thời gian làm việc và thanh toán lương.
Paycheck 

**Cơ chế phân tích:** Persistency, Message Routing, Security, Redundancy
* Persistency: Lưu trữ hồ sơ thanh toán để phục vụ báo cáo và kiểm toán.
* Message Routing: Gửi thông báo thanh toán đến ngân hàng hoặc địa chỉ email của nhân viên dựa trên phương thức thanh toán được chọn.
* Security: Đảm bảo chỉ người nhận hoặc hệ thống ngân hàng mới có thể truy cập thông tin paycheck.
* Redundancy: Lưu trữ bản sao backup để tránh mất dữ liệu thanh toán trong trường hợp lỗi hệ thống.


# Phân Tích Ca Sử Dụng: Run Payroll
1. Mô Tả
Ca sử dụng "Run Payroll" chịu trách nhiệm tính toán lương cho nhân viên dựa trên thông tin thời gian làm việc, mức lương, và các khoản khấu trừ. Hệ thống cần thu thập dữ liệu về thời gian làm việc của từng nhân viên, các loại phụ cấp, khấu trừ và thực hiện các bước tính toán để xác định tổng số tiền lương cho mỗi kỳ thanh toán. Cuối cùng, hệ thống sẽ lưu trữ và tạo báo cáo về thông tin lương.

2. Biểu Đồ Tuần Tự
![diagram](https://www.planttext.com/api/plantuml/png/T991RiCW44NtSugvG2xWHPKehRADabnW1BD0nM0DE9BFraMFr2lKniMHxUaEyT_t6mm_Nz_7b4bottf8dowWnCG0G2P7mPDjNO1kp9rn7OMCLneaUdzdUJh3g-YZxNmSc6_SnUJ6-h2A7wvbGsB_YU_aIOOpUTDx6bFDEbKbNpYm50JAV7XusupLuAqFTG_MsKJl9stmmgyJu3jdSZx17iI3OdlrA1CemltPPs7TdujxIhMjIufj-oiRh6l-os2BgAAbPMjDaUbNCnslBBa2E1EWywf_PfOlMKrVNa2pICvnl0ekBC2HWvtUzIy0003__mC0)

3. Hành Vi của Từng Lớp
PayrollService: Lớp chính điều phối việc tính lương. Nhận lệnh từ người dùng để chạy quá trình tính lương, lấy thông tin về nhân viên từ EmployeeRepository, thông tin về thời gian làm việc từ TimecardRepository, và thông tin về lương cơ bản từ SalaryCalculator.
EmployeeRepository: Quản lý truy xuất thông tin nhân viên, bao gồm loại công việc, phương thức thanh toán và các thuộc tính cơ bản như lương theo giờ hay lương tháng.
TimecardRepository: Lưu và truy xuất thông tin chấm công của nhân viên. Đảm bảo rằng hệ thống có đủ dữ liệu về số giờ làm việc để tính toán chính xác.
SalaryCalculator: Thực hiện các tính toán liên quan đến lương, bao gồm lương cơ bản, khấu trừ và các phụ cấp. Sau đó, trả về kết quả cuối cùng cho PayrollService.
PayrollReportGenerator: Tạo và lưu trữ báo cáo lương cho mỗi nhân viên sau khi tính toán hoàn tất.

4. Quan Hệ Giữa Các Lớp
PayrollService là lớp trung tâm, điều phối quá trình tính lương bằng cách tương tác với EmployeeRepository, TimecardRepository, và SalaryCalculator.
EmployeeRepository và TimecardRepository cung cấp thông tin cần thiết cho việc tính toán lương.
SalaryCalculator xử lý các phép tính phức tạp liên quan đến lương dựa trên dữ liệu từ các lớp khác.
PayrollReportGenerator tạo báo cáo dựa trên kết quả từ SalaryCalculator.

5.  Biểu Đồ Lớp Phân Tích
![diagram](https://www.planttext.com/api/plantuml/png/X5JDIWCn4BxdAK9F5UmBz205AyM38gtYEMw66ffDoYHRMCGdy-0Z-GeccwIRRYBkOM5dvljBXltv-buPoz1shIJc81H5RO2GHZ9Zw1FhKKkv0po91kW7eVx1JiN6_6f9JrfmyfaGT-rHwXvW2qTjXDNO9zGUR6gkmJ8XpHpYzprVqfr5eVQEBmsDdC-YXOOXhtAcvffPLYTC4oFXZac6_IsJJIUPuqjqJQn063ZJZQQkgOri8w-JuBfxavdZU3pUCDeDAC1SPXyA4DfL5JCOICHE8SoMvnmv5sNoK5UiXSlAaVKjAFi0zbrFXeFgrbah8wMq_mc-wmxDgyO3y98af9XIF1OUB-E76WxOzM3ElpthP3yNYvlQ0YxfR0EM9ZdAm_hDQl3AhaLukdZAtQPLiSLQEMJwWdYbLU0Vwp88XrMX8VsC51fvPezuCM2og8FNAkXyeGbK3pWrvQ7n6ZD_vcomSlwvHL8vuDmD8MG5Ylk_qIy0003__mC0)

# Phân Tích Ca Sử Dụng: Select Payment Method
1. Mô Tả
Ca sử dụng "Select Payment Method" cho phép người dùng chọn phương thức thanh toán để sử dụng trong quá trình thanh toán lương cho nhân viên. Hệ thống cung cấp các tùy chọn thanh toán khác nhau như chuyển khoản ngân hàng, tiền mặt, hoặc thẻ tín dụng, và lưu lại lựa chọn của người dùng cho từng nhân viên.

2. Biểu Đồ Tuần Tự
![diagram](https://www.planttext.com/api/plantuml/png/X9512i9034NtEKKku0Mw4AM86mLHFC3OfXYSJifCBFHiBZoILx05QUkqucv8yj__oRmUprLGu_LUMWWtTkWb4C1GD9cAntCW3rLRuemhunGFfYd9wObypHdDjOvKIU1Mt7nrDsLbfI4QjQ6Zus8PGHCyaQMi1-AUz2evV4-DT0ComIqfhcl3rbmiHOG04m4kPknt71IbcAX_vaslqbxlVzxf3TfTJKsVXIcF4LF1RE1KNC6-DChYOCQtovr4xDuJLkJoxiUXVxq1003__mC0)

3. Hành Vi của Từng Lớp
PaymentService: Đây là lớp chính điều phối việc chọn phương thức thanh toán. Lớp này nhận lệnh từ người dùng để lấy các phương thức thanh toán khả dụng và lưu lại lựa chọn của họ.
PaymentRepository: Chịu trách nhiệm quản lý các phương thức thanh toán trong cơ sở dữ liệu, bao gồm việc truy xuất danh sách các phương thức thanh toán có sẵn.
EmployeeRepository: Lớp này lưu trữ và cập nhật thông tin phương thức thanh toán đã chọn cho nhân viên.
PaymentMethod: Đại diện cho từng phương thức thanh toán (chuyển khoản, tiền mặt, thẻ tín dụng) với các thuộc tính như loại phương thức và chi tiết liên quan.

4. Quan Hệ Giữa Các Lớp
PaymentService là lớp trung tâm, điều phối việc chọn phương thức thanh toán bằng cách tương tác với PaymentRepository để lấy danh sách phương thức thanh toán khả dụng và với EmployeeRepository để lưu lại phương thức được chọn.
PaymentRepository chịu trách nhiệm cung cấp danh sách các phương thức thanh toán, để PaymentService có thể hiển thị cho người dùng.
EmployeeRepository nhận nhiệm vụ lưu trữ và cập nhật thông tin phương thức thanh toán của nhân viên khi họ hoàn tất việc chọn.

5. Biểu Đồ Lớp Phân Tích
![](https://www.planttext.com/api/plantuml/png/Z5DTIiGm47xFAOO-hM0lK6HP4Hy45TcU83OVky4sAPrOAEB9VF18Ni5qc-wsJGNp-4s-dvb9Vhw-T-nauzwhKl2RDjHOXX2YA2KplSYkWd4vcbONe0z1_M6KA5oeFS4ThTgWgalR0GygezmrsXokgJgLBiXLHgtLIdmkvFUeBMjdcsvqEC3TjbANyhN4OC0RptxKx6vcljkBs7r84AknRF7Vj1dDRluLUQW6WtJPw1HzbXNck8BphV4PZ3eOPUEK0suYoM4ZKBDqYrPwdyK-qtIxieECaZsyE5fGFLJ3S3XPKrWPl9V8_T1fp1NuYLYvEvKu4JqAZgbnq4dyi0zFlxF6ZzTm7FriiiuxMl_ocUI2c8Z-x61K_qL-0G00__y30000)

# Code java mô phỏng ca sử dụng Maintain Timecard
import java.util.ArrayList;
import java.util.Date;
import java.util.List;

// Lớp Timecard đại diện cho bản ghi chấm công của nhân viên
class Timecard {
    private Date date;
    private int hoursWorked;
    
    public Timecard(Date date, int hoursWorked) {
        this.date = date;
        this.hoursWorked = hoursWorked;
    }
    
    public Date getDate() {
        return date;
    }

    public int getHoursWorked() {
        return hoursWorked;
    }

    public void setHoursWorked(int hoursWorked) {
        this.hoursWorked = hoursWorked;
    }
    
    @Override
    public String toString() {
        return "Date: " + date + ", Hours Worked: " + hoursWorked;
    }
}

// Lớp Employee đại diện cho nhân viên có danh sách các bản ghi chấm công
class Employee {
    private String employeeId;
    private List<Timecard> timecards;

    public Employee(String employeeId) {
        this.employeeId = employeeId;
        this.timecards = new ArrayList<>();
    }
    
    public String getEmployeeId() {
        return employeeId;
    }
    
    public List<Timecard> getTimecards() {
        return timecards;
    }
    
    public void addTimecard(Timecard timecard) {
        timecards.add(timecard);
    }
    
    public void updateTimecard(Date date, int hoursWorked) {
        for (Timecard timecard : timecards) {
            if (timecard.getDate().equals(date)) {
                timecard.setHoursWorked(hoursWorked);
                return;
            }
        }
        System.out.println("Timecard not found for date: " + date);
    }
    
    public void displayTimecards() {
        System.out.println("Timecards for Employee ID: " + employeeId);
        for (Timecard timecard : timecards) {
            System.out.println(timecard);
        }
    }
}

// Lớp TimecardSystem quản lý việc chấm công của nhân viên
public class TimecardSystem {
    private List<Employee> employees;
    
    public TimecardSystem() {
        employees = new ArrayList<>();
    }
    
    public Employee findEmployee(String employeeId) {
        for (Employee employee : employees) {
            if (employee.getEmployeeId().equals(employeeId)) {
                return employee;
            }
        }
        return null;
    }
    
    public void addEmployee(String employeeId) {
        Employee employee = new Employee(employeeId);
        employees.add(employee);
    }

    public void addTimecard(String employeeId, Date date, int hoursWorked) {
        Employee employee = findEmployee(employeeId);
        if (employee != null) {
            employee.addTimecard(new Timecard(date, hoursWorked));
            System.out.println("Timecard added successfully.");
        } else {
            System.out.println("Employee not found.");
        }
    }
    
    public void updateTimecard(String employeeId, Date date, int hoursWorked) {
        Employee employee = findEmployee(employeeId);
        if (employee != null) {
            employee.updateTimecard(date, hoursWorked);
            System.out.println("Timecard updated successfully.");
        } else {
            System.out.println("Employee not found.");
        }
    }
    
    public void displayEmployeeTimecards(String employeeId) {
        Employee employee = findEmployee(employeeId);
        if (employee != null) {
            employee.displayTimecards();
        } else {
            System.out.println("Employee not found.");
        }
    }

    public static void main(String[] args) {
        TimecardSystem system = new TimecardSystem();
        
        // Thêm nhân viên mới
        system.addEmployee("E001");
        
        // Thêm bản ghi chấm công cho nhân viên
        Date date1 = new Date(); // Giả định ngày hiện tại
        system.addTimecard("E001", date1, 8);
        
        // Hiển thị bản ghi chấm công của nhân viên
        system.displayEmployeeTimecards("E001");
        
        // Cập nhật bản ghi chấm công của nhân viên
        system.updateTimecard("E001", date1, 9);
        
        // Hiển thị lại bản ghi chấm công sau khi cập nhật
        system.displayEmployeeTimecards("E001");
    }
}
