# ***Thiết kế các lớp hệ thống "Payroll ystem"***

## 1. Lớp Employee
**Mục đích: Quản lý thông tin nhân viên.**
+ **Operations:**
- Thêm một nhân viên mới vào hệ thống.
- Cập nhật thông tin của nhân viên (chức vụ, lương, trạng thái...).
- Xóa thông tin một nhân viên khỏi hệ thống.
- Lấy thông tin chi tiết của nhân viên.
- Cập nhật trạng thái của nhân viên (Active, On Leave, Resigned...).

## 2. Lớp Timecard
**Mục đích: Quản lý thông tin chấm công của nhân viên.**
**Operations:**
+ Thêm một bản ghi chấm công mới.
+ Cập nhật số giờ làm việc trong bản ghi chấm công.
+ Xóa bản ghi chấm công khỏi hệ thống.
+ Lấy danh sách các bản ghi chấm công của một nhân viên.
+ Lấy thông tin chi tiết của một bản ghi chấm công.

## 3. Lớp Payroll
**Mục đích: Xử lý và quản lý bảng lương.**
**Operations:**
+ Tính lương cho một nhân viên dựa trên thông tin chấm công và lương cơ bản.
+ Tạo phiếu lương chi tiết cho nhân viên.
+ Xử lý bảng lương cho tất cả nhân viên.
+ Thêm một bản ghi lương mới vào hệ thống.
+ Lấy thông tin chi tiết của một bản ghi bảng lương.

## 4. Tương tác giữa các lớp thông qua Operations
+ Lớp Employee gọi addTimecard hoặc deleteTimecard từ lớp Timecard để quản lý chấm công.
+ Lớp Payroll gọi getTimecardsByEmployee từ lớp Timecard để tính toán tổng lương.
+ Lớp Payroll sử dụng thông tin từ lớp Employee để tạo phiếu lương và báo cáo chi tiết.

## 1. Lớp Employee - Biểu đồ Trạng thái
**Lớp Employee có thể có nhiều trạng thái trong quá trình làm việc của nhân viên, và mỗi trạng thái này phản ánh sự thay đổi trong tình trạng công việc của họ.**
### Các trạng thái:
+ Hired: Nhân viên mới được tuyển dụng, nhưng chưa bắt đầu làm việc.
+ Active: Nhân viên đang làm việc và có thể thực hiện các công việc bình thường.
+ On Leave: Nhân viên đang trong kỳ nghỉ phép hoặc nghỉ ốm.
+ Resigned: Nhân viên đã nghỉ việc hoặc chấm dứt hợp đồng.
**Chuyển đổi trạng thái:**
+ Hired → Active: Khi nhân viên bắt đầu công việc.
+ Active → On Leave: Khi nhân viên yêu cầu nghỉ phép.
+ On Leave → Active: Khi nhân viên quay lại làm việc sau khi nghỉ.
+ Active → Resigned: Khi nhân viên xin nghỉ việc.

![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bUqLgo2hgwTWaTcKMeA5nUO0Wiu9fTabgKgM2c0bORd5sLhQ7911K7o_da-gObW1KMfXQMfnILWBb0DJ0B5aABKajAYFBUY_5oOCYIZWbABCzFpWFQ2r86OG6c7rBmKaFi00000__y30000)

## 2. Lớp Payroll - Biểu đồ Trạng thái
**Lớp Payroll chịu trách nhiệm về việc tính toán và xử lý bảng lương. Quá trình này có các trạng thái thay đổi trong từng kỳ tính lương.**
### Các trạng thái:
+ Initialized: Bảng lương đã được khởi tạo, nhưng chưa bắt đầu tính toán.
+ Calculating: Quá trình tính toán lương đang được thực hiện.
+ Completed: Bảng lương đã hoàn tất, các tính toán đã được hoàn thành và bảng lương có thể được phát hành.
### Chuyển đổi trạng thái:
+ Initialized → Calculating: Khi quá trình tính toán bảng lương bắt đầu.
+ Calculating → Completed: Khi quá trình tính toán lương hoàn tất.
  
![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bUqLgo2hgwTWcTUPabcOavcLMeA5nSI1opfd9YJN9gJM9APbwvWfG3M6v1OMPIVawEXoOKi2LQSdrkGare2r6gba9QPbrcS0LUHdmTKxv2QbmAo6G000F__0m00)

