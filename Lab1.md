# LAB 1

# PHÂN TÍCH KIẾN TRÚC, CƠ CHẾ, CA SỬ DỤNG

# 1. Phân tích kiến trúc

 ***1.1 Kiến trúc đề xuất: Hệ thống Payroll System sử dụng kiến trúc 3 lớp:***

> - Presentation Layer
> - Business Logic Layer
> - Data Access Layer

***1.2 Lý do lựa chọn:***  
   Kiến trúc 3 lớp giúp hệ thống tách biệt rõ ràng giữa giao diện người dùng, logic nghiệp vụ, và quản lý dữ liệu. Điều này giúp cải thiện khả năng bảo trì, mở rộng, và bảo mật.

***1.3 Ý nghĩa các thành phần trong kiến trúc:***

>> **Presentation Layer:**

* Cung cấp giao diện người dùng để nhân viên có thể nhập thông tin, lựa chọn phương thức thanh toán và xem báo cáo*.</p>
 
 * Các thành phần trong lớp này gồm:

**TimecardEntry:** Nhập thông tin về thời gian làm việc và mã số dự án.</p>
**OrderManagement:** Quản lý đơn hàng để ghi lại doanh số bán hàng cho nhân viên hoa hồng.</p>
**PaymentOptions:** Cho phép nhân viên chọn phương thức thanh toán.</p>
</p>

>> *Business Logic Layer:* </p>
- Xử lý tất cả các logic nghiệp vụ như tính toán thanh toán, quản lý nhân viên, và tạo báo cáo.</p>
 * Các thành phần trong lớp này gồm:</p>
**PayrollProcessor:** Tính toán lương theo loại hợp đồng (giờ, tháng, hoa hồng).</p>
**EmployeeManager:** Quản lý thông tin cơ bản của nhân viên.</p>
**Reporting:** Tạo các báo cáo về giờ làm việc, doanh thu, và lương.</p>

>> *Data Access Layer:*

* Tương tác với cơ sở dữ liệu hiện có và cơ sở dữ liệu mới để lưu trữ thông tin liên quan đến Payroll.</p>
* Các thành phần trong lớp này gồm:    </p>
**DB2Access:** Đọc dữ liệu từ cơ sở dữ liệu DB2 của Acme.</p>
**PayrollDataAccess:** Lưu trữ dữ liệu mới liên quan đến timecard, thanh toán và báo cáo của Payroll.</p>

***1.4 Pakage***

![Diagram](https://www.planttext.com/api/plantuml/png/h5MnRjim4Dtz5GSlLOTaoEWXI9q4pQ0wJY44NGcAa8XAf41HWr1axbIWdRlKBR8K2DAXIqqK6LJaF_W5-OKSgRHmKYkHusYW0PlllNllTEShSx5JQg9qbMU3GK7eMv8m61vOynvqQiqdaS2Kr4fcsH3U3G0VV_ox6LhpkO2Nd4Y8EQ8415F5IYOqqLmA24dDrFE_MFVGZ9Gb32UfdPyL4E67WLqyJtFORNwYNX3nd56YudsXLNqBUtANvQYoys-eqlo6FnylPm8EcY-Eub35JBqY0clCiPRxIQBcL-rAC1y4raD42f5iPiu9gHtwi71MoYKa9vs9X3BX52P9wa8fuDYQKmZ6LSa5GydsryvitbXpvZs5bp_GLE8hSJsOAaaHBrNlL2PfyrN0CM--ev_zlCXapLWRp0CausOciIDu1AzP8PNc8baQmJBxaQemKj_XFMlE8NGnL13i4KtW1QK-X2xxY-3n5eB6MotaWJOkrxoReIkXa-x6pJCugeY0r8r1WZJd16Wpev1vSrf9vFDVtDZseDwpiB6n_PZNP0IbUozYl2EIHSLLI1QqL-dH24tZRUfkhnFH2bE_kRdTSn96M01chhcTNnIjJl-zi9PC_ytnM9bMfnVGIzmtExUQk0Plt-7wNw__Odf2qOv5zZGAk31sc8ZTt-Sr0000__y30000)

# 2. Cơ chế phân tích 

   Dưới đây là các cơ chế quan trọng cần giải quyết trong hệ thống "Payroll System" cùng với lý do đề xuất để đảm bảo hệ thống hoạt động hiệu quả và đáp ứng đầy đủ yêu cầu:

**1. Cơ chế Xử lý Thanh toán Tự động**

Mô tả: Hệ thống sẽ tự động tính toán lương và thực hiện thanh toán vào thứ Sáu hàng tuần cho nhân viên tính lương theo giờ, và vào ngày làm việc cuối cùng của tháng cho nhân viên nhận lương cố định và có hoa hồng.
Lý do: Điều này giúp đảm bảo nhân viên được trả lương đúng hạn và phù hợp với các quy định thanh toán khác nhau (theo giờ, cố định, và theo doanh số bán hàng). </p>

**2. Cơ chế Phân loại Nhân viên** </p>

Mô tả: Phân loại nhân viên thành các loại như: nhân viên tính lương theo giờ, nhân viên nhận lương cố định, và nhân viên nhận lương hoa hồng. Mỗi loại sẽ có cơ chế tính lương riêng.
Lý do: Mỗi loại nhân viên có yêu cầu tính toán lương khác nhau, vì vậy việc phân loại này giúp hệ thống linh hoạt trong tính toán và thực hiện thanh toán chính xác.</p>

**3. Cơ chế Tính lương Overtime (làm thêm giờ)** </p>

Mô tả: Đối với nhân viên nhận lương theo giờ, nếu làm việc hơn 8 giờ/ngày, thời gian làm thêm sẽ được trả 1,5 lần mức lương bình thường.
Lý do: Đảm bảo tính toán chính xác cho các nhân viên làm việc vượt mức thời gian quy định và tuân thủ chính sách công ty.
</p>

**4. Cơ chế Bảo mật Dữ liệu** </p>

Mô tả: Chỉ Payroll Administrator mới có quyền truy cập và thay đổi thông tin nhân viên, đảm bảo nhân viên chỉ có quyền truy cập và chỉnh sửa thông tin cá nhân của chính họ (timecard và đơn hàng).
Lý do: Đảm bảo tính bảo mật và riêng tư cho dữ liệu nhân viên, đồng thời hạn chế quyền truy cập để tránh các rủi ro liên quan đến bảo mật.
</p>

**5. Cơ chế Truy cập Dữ liệu DB2** </p>

Mô tả: Hệ thống chỉ đọc dữ liệu từ cơ sở dữ liệu DB2 của hệ thống quản lý dự án để lấy các thông tin mã số dự án và thông tin liên quan.
Lý do: Đảm bảo hệ thống mới tương thích với cơ sở dữ liệu hiện tại của công ty, tránh việc thay đổi và phát sinh chi phí không cần thiết.
</p>

**6. Cơ chế Báo cáo cho Nhân viên** </p>

Mô tả: Nhân viên có thể truy vấn số giờ đã làm, tổng giờ làm theo từng dự án, tổng lương nhận được từ đầu năm, số ngày nghỉ phép còn lại, v.v.
Lý do: Đáp ứng yêu cầu thông tin của nhân viên để họ dễ dàng theo dõi công việc và các khoản thu nhập, thời gian nghỉ phép.
</p>

**7. Cơ chế Chọn phương thức thanh toán** </p>
Mô tả: Nhân viên có thể chọn phương thức nhận lương qua bưu điện, chuyển khoản ngân hàng hoặc nhận trực tiếp tại văn phòng.
Lý do: Cung cấp sự linh hoạt cho nhân viên trong việc nhận lương, đáp ứng nhu cầu đa dạng của nhân viên về hình thức thanh toán.</P>

# **Danh sách cơ chế phân tích đề xuất:**
*Xử lý Thanh toán Tự động
*Phân loại Nhân viên
*Tính lương Overtime (làm thêm giờ)
*Bảo mật Dữ liệu
*Truy cập Dữ liệu DB2
*Báo cáo cho Nhân viên
*Chọn phương thức thanh toán </p>

# 3. Phân tích ca sử dụng Payment
Xác định các lớp phân tích cho ca sử dụng Payment, mô tả được hành vi thông qua biểu đồ sequence, xác định được nhiệm vụ của từng lớp phân tích, xác định một số thuộc tính và quan hệ giữa các lớp phân tích. Kết quả mong đợi là các biểu đồ lớp mô tả lớp phân tích và giải thích.
# 4. Phân tích ca sử dụng Maintain Timecard
Xác định các lớp phân tích cho ca sử dụng Maintain Timecard, mô tả được hành vi thông qua biểu đồ sequence, xác định được nhiệm vụ của từng lớp phân tích, xác định một số thuộc tính và quan hệ giữa các lớp phân tích. Kết quả mong đợi là các biểu đồ lớp mô tả lớp phân tích và giải thích.
# 5. Hợp nhất kết quả phân tích
Tiến hành hợp nhất kết quả phân tích 02 ca sử dụng trên và viết tài liệu mô tả.

