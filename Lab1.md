# LAB 1

# PHÂN TÍCH KIẾN TRÚC, CƠ CHẾ, CA SỬ DỤNG

# 1. Phân tích kiến trúc

 ***1.1 Kiến trúc đề xuất: Hệ thống Payroll System sử dụng kiến trúc 3 lớp:***

> - Presentation Layer
> - Business Logic Layer
> - Data Access Layer

***1.2 Lý do lựa chọn:***  Kiến trúc 3 lớp giúp hệ thống tách biệt rõ ràng giữa giao diện người dùng, logic nghiệp vụ, và quản lý dữ liệu. Điều này giúp cải thiện khả năng bảo trì, mở rộng, và bảo mật.

***1.3 Ý nghĩa các thành phần trong kiến trúc:***

>> **Presentation Layer:**

* Cung cấp giao diện người dùng để nhân viên có thể nhập thông tin, lựa chọn phương thức thanh toán và xem báo cáo*.</p>
 
 * Các thành phần trong lớp này gồm:

* TimecardEntry: Nhập thông tin về thời gian làm việc và mã số dự án.</p>
* OrderManagement: Quản lý đơn hàng để ghi lại doanh số bán hàng cho nhân viên hoa hồng.</p>
* PaymentOptions: Cho phép nhân viên chọn phương thức thanh toán.</p>
</p>

>> *Business Logic Layer:* </p>
- Xử lý tất cả các logic nghiệp vụ như tính toán thanh toán, quản lý nhân viên, và tạo báo cáo.</p>
Các thành phần trong lớp này gồm:</p>
PayrollProcessor: Tính toán lương theo loại hợp đồng (giờ, tháng, hoa hồng).</p>
EmployeeManager: Quản lý thông tin cơ bản của nhân viên.</p>
Reporting: Tạo các báo cáo về giờ làm việc, doanh thu, và lương.</p>

>> *Data Access Layer:*

- Tương tác với cơ sở dữ liệu hiện có và cơ sở dữ liệu mới để lưu trữ thông tin liên quan đến Payroll.</p>
Các thành phần trong lớp này gồm:    </p>
<em>DB2Access:</em> Đọc dữ liệu từ cơ sở dữ liệu DB2 của Acme.</p>
<em>PayrollDataAccess:</em> Lưu trữ dữ liệu mới liên quan đến timecard, thanh toán và báo cáo của Payroll.</p>
# 2. Cơ chế phân tích
Đề xuất các cơ chế cần giải quyết trong bài toán và giải thích lý do. Kết quả mong đợi là một danh sách cơ chế phù hợp.
# 3. Phân tích ca sử dụng Payment
Xác định các lớp phân tích cho ca sử dụng Payment, mô tả được hành vi thông qua biểu đồ sequence, xác định được nhiệm vụ của từng lớp phân tích, xác định một số thuộc tính và quan hệ giữa các lớp phân tích. Kết quả mong đợi là các biểu đồ lớp mô tả lớp phân tích và giải thích.
# 4. Phân tích ca sử dụng Maintain Timecard
Xác định các lớp phân tích cho ca sử dụng Maintain Timecard, mô tả được hành vi thông qua biểu đồ sequence, xác định được nhiệm vụ của từng lớp phân tích, xác định một số thuộc tính và quan hệ giữa các lớp phân tích. Kết quả mong đợi là các biểu đồ lớp mô tả lớp phân tích và giải thích.
# 5. Hợp nhất kết quả phân tích
Tiến hành hợp nhất kết quả phân tích 02 ca sử dụng trên và viết tài liệu mô tả.

