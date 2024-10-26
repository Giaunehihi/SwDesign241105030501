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

***1. Xác thực và Phân quyền Người dùng*** </p>
* **Giải thích:** Đảm bảo chỉ những nhân viên được ủy quyền mới có thể truy cập và chỉnh sửa thông tin cá nhân.

* **Lý do:** Bảo vệ dữ liệu nhạy cảm và tuân thủ quy định bảo mật.

***2. Quản lý Thời gian công***
* **Giải thích:** Cho phép nhân viên nhập thời gian làm việc và tự động tính giờ làm thêm.

* **Lý do:** Đảm bảo tính toán lương chính xác và theo dõi hiệu suất làm việc.

***3. Nhập Đơn Đặt hàng và Tính toán Hoa hồng***
* **Giải thích:** Nhân viên nhập đơn hàng, hệ thống tính toán hoa hồng theo tỷ lệ.

* **Lý do:** Đảm bảo trả lương công bằng cho nhân viên bán hàng, khuyến khích hiệu suất.

***4. Xử lý Tiền lương Tự động***
* **Giải thích:** Hệ thống tự động tính toán và phát lương vào lịch cố định.

* **Lý do:** Tiết kiệm thời gian và giảm sai sót do con người.

***5. Báo cáo cho Nhân viên***
* **Giải thích:** Cung cấp thông tin về số giờ làm việc, thu nhập, và thời gian nghỉ phép.

* **Lý do:** Tăng tính minh bạch và giúp nhân viên theo dõi tài chính cá nhân.

***6. Quản lý Thông tin Nhân viên***
* **Giải thích:** Quản trị viên có thể thêm, cập nhật, hoặc xóa thông tin về nhân viên.

* **Lý do:** Đảm bảo giữ thông tin chính xác cho việc tính lương và quản lý.

***7. Tích hợp với Cơ sở Dữ liệu Hiện có***
* **Giải thích:** Hệ thống truy cập thông tin từ Cơ sở Dữ liệu Quản lý Dự án mà không thay đổi.

* **Lý do:** Duy trì tính toàn vẹn dữ liệu và tiết kiệm chi phí triển khai.

***8. Thông báo và Cảnh báo***
* **Giải thích:** Gửi thông báo cho nhân viên về ngày thanh toán và thông tin cập nhật khác.

* **Lý do:** Đảm bảo nhân viên luôn được thông tin kịp thời, nâng cao sự tương tác.

### Kết quả mong đợi của cơ chế phân tích trong hệ thống "Payroll System" bao gồm:###

**Chính xác trong Thanh toán:** Giảm thiểu sai sót, đảm bảo nhân viên nhận lương đúng hạn.
**Hài lòng của Nhân viên:** Tăng cường động lực làm việc và giảm tỷ lệ nghỉ việc.
**Bảo mật Thông tin:** Bảo vệ dữ liệu nhân viên, giảm rủi ro vi phạm bảo mật.
**Tiết kiệm Chi phí và Thời gian:** Tự động hóa quy trình thanh toán, tối ưu hóa nguồn lực.
**Tuân thủ Pháp luật:** Đảm bảo công ty tuân thủ các quy định về tiền lương và lao động.
**Minh bạch Thông tin:** Nhân viên dễ dàng truy cập thông tin lương và giờ làm.
**Phản hồi Nhanh chóng:** Giảm thời gian xử lý các yêu cầu và thắc mắc của nhân viên.
**Linh hoạt Thích ứng:** Điều chỉnh dễ dàng với thay đổi về chính sách và quy định.
</p>

# 3. Phân tích ca sử dụng Payment
*Các lớp phân tích cho ca sử dụng "Payment":*

*NhânViên (Employee):*

* Mô tả: Đại diện cho nhân viên trong hệ thống, chứa thông tin cá nhân và phương thức thanh toán của họ.

**Thuộc tính:**

      - mãNhânViên: String
      - tên: String
      - địaChỉ: String
      - phươngThứcThanhToán: String
      - tàiKhoảnNgânHàng: String
      - HệThốngLương (PayrollSystem):


* Mô tả: Chịu trách nhiệm tính toán lương cho nhân viên dựa trên số giờ làm việc hoặc doanh thu từ hoa hồng.
  
**Thuộc tính:**
      - danhSáchNhânViên: List<NhânViên>
      - Phương thức:
      - tínhToánLương()
      - gửiThôngBáo()
      - ThanhToán (Payment):

* Mô tả: Thông tin liên quan đến giao dịch thanh toán cho nhân viên.
  
**Thuộc tính:**

      - sốTiền: Double
      - ngàyThanhToán: Date
      - trạngThái: String (thành công, thất bại)
      - NgânHàng (Bank):

* Mô tả: Chịu trách nhiệm thực hiện các giao dịch thanh toán từ hệ thống.
  
**Thuộc tính:**

      - tênNgânHàng: String
      - sốTàiKhoảnNgânHàng: String
      - XửLýThanhToán (PaymentProcessor):

* Mô tả: Thực hiện các thao tác xử lý thanh toán và giao tiếp với ngân hàng để hoàn tất giao dịch.
  
**Thuộc tính:**

      - mãGiaoDịch: String
      - trạngTháiGiaoDịch: String
      
# 4. Phân tích ca sử dụng Maintain Timecard
Xác định các lớp phân tích cho ca sử dụng Maintain Timecard, mô tả được hành vi thông qua biểu đồ sequence, xác định được nhiệm vụ của từng lớp phân tích, xác định một số thuộc tính và quan hệ giữa các lớp phân tích. Kết quả mong đợi là các biểu đồ lớp mô tả lớp phân tích và giải thích.
# 5. Hợp nhất kết quả phân tích
Tiến hành hợp nhất kết quả phân tích 02 ca sử dụng trên và viết tài liệu mô tả.

