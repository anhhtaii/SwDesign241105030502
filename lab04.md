# Các Ca Sử Dụng Chính
## Login:
Người dùng nhập tên đăng nhập và mật khẩu.
Hệ thống xác thực thông tin và cấp quyền truy cập nếu thông tin hợp lệ.
## Maintain Timecard:
Nhân viên truy cập timecard hiện tại, nhập giờ làm việc cho các mã công việc, và lưu thông tin.
Hệ thống kiểm tra, cập nhật và lưu timecard vào cơ sở dữ liệu.
## Run Payroll:
Hệ thống xác định thời gian trả lương.
Tính toán lương dựa trên giờ làm, lương cơ bản, và các đơn hàng hoa hồng.
Tạo phiếu lương (Paycheck) và gửi dữ liệu đến ngân hàng hoặc in phiếu lương.
Thiết Kế Các Ca Sử Dụng
### 1. Login
+ Thành phần liên quan:
Boundary: LoginForm (Form đăng nhập).
Control: Không yêu cầu.
Entity: Không yêu cầu.
+ Luồng thực hiện:
Người dùng nhập thông tin.
LoginForm gửi thông tin đến cơ chế xác thực.
Hệ thống kiểm tra tính hợp lệ và trả kết quả (chấp nhận/từ chối).
### 2. Maintain Timecard
+ Thành phần liên quan:
Boundary: TimecardForm (Form quản lý timecard).
Control: TimecardController (Xử lý dữ liệu timecard).
Entity: Timecard, Employee.
+ Luồng thực hiện:
Employee mở TimecardForm.
TimecardController lấy dữ liệu timecard hiện tại từ ProjectManagementDatabase.
Người dùng nhập dữ liệu (giờ làm việc, mã công việc).
TimecardController cập nhật và lưu thông tin mới.
### 3. Run Payroll
+ Thành phần liên quan:
Boundary: SystemClockInterface, PrinterInterface, BankSystem.
Control: PayrollController.
Entity: Employee, Paycheck, Timecard, PurchaseOrder.
+ Luồng thực hiện:
SystemClockInterface khởi động ca sử dụng.
PayrollController xác định danh sách nhân viên cần tính lương.
Hệ thống tính toán lương dựa trên dữ liệu:
Giờ làm từ Timecard.
Đơn hàng từ PurchaseOrder (nếu là nhân viên hoa hồng).
Tạo và lưu phiếu lương (Paycheck).
Gửi thông tin thanh toán đến BankSystem hoặc in phiếu lương thông qua PrinterInterface.
### 1. Subsystem Context Diagrams
#### Các subsystem được định nghĩa rõ ràng:
##### BankSystem:
+ Giao tiếp với ngân hàng để thực hiện giao dịch (direct deposit).
+ Sử dụng interface: IBankSystem.
##### PrintService:
+ Hỗ trợ in phiếu lương.
+ Sử dụng interface: IPrintService.
##### ProjectManagementDatabase:
+ Kết nối với cơ sở dữ liệu legacy để lấy mã công việc.
+ Sử dụng interface: IProjectManagementDatabase.
### 2. Mapping Analysis Classes to Design Elements
#### Phần này chỉ rõ mối liên hệ giữa các lớp phân tích và phần tử thiết kế:
+ Các lớp như Timecard, Paycheck, và Employee thuộc tầng Business Services.
+ Các subsystem như BankSystem, PrintService, và ProjectManagementDatabase được định nghĩa như External System Interfaces để cách ly hệ thống nội bộ khỏi các dịch vụ bên ngoài.
### 3. Kiến trúc phân lớp
#### Hệ thống được tổ chức thành các lớp:
#### Application Layer:
Quản lý các chức năng đặc thù của ứng dụng, ví dụ như PayrollController.
### Business Services Layer:
Xử lý các nghiệp vụ cốt lõi như quản lý lương, thời gian làm việc.
### Middleware Layer:
Cung cấp các dịch vụ giao tiếp với hệ thống bên ngoài và các tiện ích.

