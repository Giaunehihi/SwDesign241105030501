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
*3.1 Các lớp phân tích cho ca sử dụng "Payment":*

*NhânViên (Employee):*

* Mô tả: Đại diện cho nhân viên trong hệ thống, chứa thông tin cá nhân và phương thức thanh toán của họ.

**Thuộc tính:**

      - mãNhânViên: String
      - tên: String
      - địaChỉ: String
      - phươngThứcThanhToán: String
      - tàiKhoảnNgânHàng: String

*HệThốngLương (PayrollSystem):*

* Mô tả: Chịu trách nhiệm tính toán lương cho nhân viên dựa trên số giờ làm việc hoặc doanh thu từ hoa hồng.
  
**Thuộc tính:**
      - danhSáchNhânViên: List<NhânViên>
      - Phương thức:
      - tínhToánLương()
      - gửiThôngBáo()
      
*ThanhToán (Payment):*

* Mô tả: Thông tin liên quan đến giao dịch thanh toán cho nhân viên.
  
**Thuộc tính:**

      - sốTiền: Double
      - ngàyThanhToán: Date
      - trạngThái: String (thành công, thất bại)
      
*NgânHàng (Bank):*

* Mô tả: Chịu trách nhiệm thực hiện các giao dịch thanh toán từ hệ thống.
  
**Thuộc tính:**

      - tênNgânHàng: String
      - sốTàiKhoảnNgânHàng: String
      
*XửLýThanhToán (PaymentProcessor):*

* Mô tả: Thực hiện các thao tác xử lý thanh toán và giao tiếp với ngân hàng để hoàn tất giao dịch.
  
**Thuộc tính:**

      - mãGiaoDịch: String
      - trạngTháiGiaoDịch: String
      
*3.2  Biểu Đồ Tuần Tự (Sequence Diagram)*

![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aO9Vnk55UM6PXrVbSHK09JAJCmiIyqeKF1xkRW_9UBXxObwwpx4DnnRcfQD8HppSlTRdyDwGZCIyZ93ymmjHDVkb0ytqEBm0g8aBORw2hXqMOwqKAW-lAbL8VhXhUId2E0rDBaobk0meERmMgWqgX5CtXhEj52hGXO2QCPI1z28y1RGHQFB6v92CJFVCn7oNXxkxapE0sX0gSDXLKlHmrsBlXxlsbmIM0baech7QYSstm91QM-2N0IHBWDAJWuyj92BO4B40SlpXBNdfJeSNveS0tGDK499nU64cYY4EgNafe2G20000__y30000)

*3.3 Nhiệm Vụ của Các Lớp Phân Tích*

*NhânViên (Employee):*

* Gửi yêu cầu thanh toán tới hệ thống.
* Nhận thông báo về trạng thái thanh toán.

*HệThốngLương (PayrollSystem):*

* Tính toán số tiền lương dựa trên giờ làm việc hoặc hoa hồng.
* Gửi yêu cầu xử lý thanh toán đến lớp XửLýThanhToán.
  
*ThanhToán (Payment):*

* Lưu trữ thông tin thanh toán cho mỗi nhân viên, bao gồm số tiền và trạng thái giao dịch.
  
*NgânHàng (Bank):*

* Thực hiện các giao dịch thanh toán cho nhân viên và trả kết quả về lớp xử lý thanh toán.

*XửLýThanhToán (PaymentProcessor):*

* Nhận yêu cầu thanh toán từ hệ thống lương.
* Xử lý giao dịch với ngân hàng và cập nhật trạng thái thanh toán.

*3.4. Biểu Đồ Lớp (Class Diagram)*

![Diagram](https://www.planttext.com/api/plantuml/png/V5F1IiD04BtdAuQSL6ZHQv1Ij631qak3U8rfsLriDwNPWY8UF8buwXVOs9D2GQ6dBjB3IlzZly1VSDAkoTAqvZZlpRoPzpO_Sb6DHJ0GmrxN2Rj174EJgbT-mTGxXpi7y2j1JqtogWSjCM2S64mKIzyZBP-3KwhbqmRIfykFPSA9ZzXRwDE0KpzIIN7cc9tJICydl4bGjwx6d6ISUyTiclTdcyPQZdocvGEEh4N3gsx709oeyQqjM0l47oO6UhvQIYMig5BNyZ7TTyH9OxrzfjR6SIsLXDHsfy5YSPmNAYiku4rJesscxEqRX6WvPIW-u-H49H7MC-rBX1hgQykX6CaP2w8QEXtIJVkiUtQG06usHzkwkUkPO9hpbZ0is_yDpPY0FdvYxjPQQrdhqRb7BfHA5N0Fo-K3rmxP0u67HL1njcIIjbXJa6kU6kQpkwDei0VNI7jXlf4gCbPAkK4U43m67zryqKT-jSFRwS_q2m00__y30000)

*3.5 Giải Thích Biểu Đồ Lớp*

**NhânViên:** Có thể tạo nhiều ThanhToán. Điều này phản ánh rằng mỗi nhân viên có thể nhận nhiều khoản thanh toán khác nhau trong suốt thời gian làm việc.

**HệThốngLương:** Tương tác với NhânViên để nhận thông tin và thực hiện tính toán. Nó sẽ gọi đến lớp XửLýThanhToán để xử lý thanh toán.

**XửLýThanhToán:** Là cầu nối giữa HệThốngLương và NgânHàng, đảm bảo rằng các giao dịch thanh toán được thực hiện một cách an toàn và chính xác.

**NgânHàng:** Chịu trách nhiệm thực hiện giao dịch thanh toán cho nhân viên và trả kết quả về lớp XửLýThanhToán.


# 4. Phân tích ca sử dụng Maintain Timecard
**4.1 Các lớp phân tích cho ca sử dụng "Maintain Timecard":**

*NhânViên (Employee):*

* Mô tả: Đại diện cho nhân viên trong hệ thống, chứa thông tin cá nhân và quyền truy cập vào thời gian làm việc của họ.
***Thuộc tính:***
  
   - mãNhânViên: String
   - tên: String
   - địaChỉ: String
   - thờiGianLàmViệc: List<ThờiGian>

*ThờiGian (Timecard):*

* Mô tả: Đại diện cho thời gian làm việc của nhân viên, chứa thông tin về giờ làm việc và các thông tin liên quan.

***Thuộc tính:***

  - ngày: Date
  - sốGiờ: Double
  - mãSốChiPhí: String
  - trạngThái: String (đã gửi, chưa gửi)

 *HệThốngLương (PayrollSystem):*

* Mô tả: Chịu trách nhiệm quản lý và cập nhật thông tin thời gian làm việc của nhân viên.

***Thuộc tính:***

   - danhSáchNhânViên: List<NhânViên>
***Phương thức:***
   - cậpNhậtThờiGian()
   - lưuThờiGian()
   - XácNhận (Approval):

* Mô tả: Chịu trách nhiệm quản lý trạng thái phê duyệt thời gian làm việc của nhân viên.
***Thuộc tính:***
   - trạngTháiPhêDuyệt: String (đã phê duyệt, chưa phê duyệt)
   - ngườiPhêDuyệt: String
     
**4.2 Biểu Đồ Tuần Tự (Sequence Diagram)**
     ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aO9Vnk55UM6PXrVbSHK09JAJCmiIyqeKF1xkRW_9UBXxObwwpx4DnnRcfQD8WwJcPhfd9gBgYZYyCDalu-6kjNbSN0Y35NJji9XdfL1vU5MfGlB3NSjBdO5Q2i0QIn0cQsXoOUe2cOLGOgLGyd3NmdmKFGWEBdlJ7-vUcncISNXBNdf8PXuH5YAyXUpeW8p3grnAAu4wIe0w4MfmMLjIz73NuX0W0UG1RL-OYMe0TgiHeGWq0EnafyD03oEPWXHsG5CSKlDIG94B0000__y30000)

**4.3 Nhiệm Vụ của Các Lớp Phân Tích**
*NhânViên (Employee):*

* Gửi yêu cầu cập nhật thời gian làm việc.
* Nhận thông báo về trạng thái cập nhật thời gian.

*ThờiGian (Timecard):*

* Lưu trữ thông tin về thời gian làm việc của nhân viên.
* Cung cấp thông tin cho hệ thống lương khi cần thiết.

*HệThốngLương (PayrollSystem):*

* Cập nhật thông tin thời gian làm việc của nhân viên.
* Gửi yêu cầu phê duyệt đến lớp xác nhận.

*XácNhận (Approval):*

* Kiểm tra và xác nhận thời gian làm việc của nhân viên.
* Trả lại trạng thái phê duyệt cho hệ thống lương.  

**4.4 Biểu Đồ Lớp (Class Diagram)**

 ![Diagram](https://www.planttext.com/api/plantuml/png/T5AnQiCm4Dtz5OUdjf3GhgQOG0Bf448X8NHr7MC9R2NOyX1Avr8wvGC2IJiK307FyT11nV_XByWlz9GQoN5h3HhUUtVttad7_AiNSoVYIHWORk34COo9U6SpAb86JmRWwK0eFZHgmOH7bFaLn_z2t-ioVtFwfCnVcsB4DdH87JOIst16o_p5jM14OtuxLPHjF1kL5mqgBymNsvK50uTx5HAN-Ng8hJQ8BfB7mDEk9qZr2RqdOjzq4fM77VEdHEoeejJSEpGcPw-PFogo0eLg_jnXP29sBgblv9H00_P92-2MX_roJF3cEid5PSK6HPQSmMhy0_O_bUdOTRyO9nqaA_J86wcONsIoOPi2OAcPvkpQmvit9dGwDfZNtUwLMNy62pWQMO1j_BCZMLBhWjfVOefvsYlEkikbj4jhYx5W9T94hlXJ5lGyDfT_-0S00F__0m00)

**4.5 Giải Thích Biểu Đồ Lớp**
* NhânViên: Có thể tạo nhiều ThờiGian. Điều này phản ánh rằng mỗi nhân viên có thể ghi lại nhiều khoảng thời gian khác nhau trong suốt thời gian làm việc của họ.

* ThờiGian: Lưu trữ thông tin về thời gian làm việc của nhân viên, bao gồm ngày làm việc, số giờ làm việc và mã số chi phí liên quan.

* HệThốngLương: Quản lý danh sách nhân viên và cập nhật thông tin thời gian làm việc của họ.

* XácNhận: Kiểm tra và phê duyệt thời gian làm việc trước khi lưu trữ vào hệ thống lương.


# 5. Hợp nhất kết quả phân tích
5.1. Giới Thiệu
Tài liệu này mô tả kết quả phân tích cho hai ca sử dụng "Payment" và "Maintain Timecard" trong hệ thống quản lý lương của Acme, Inc. Mục tiêu là cải thiện quy trình thanh toán và ghi nhận thời gian làm việc của nhân viên.

2. Ca Sử Dụng "Payment"
2.1 Mô Tả
Ca sử dụng "Payment" xử lý và tạo hóa đơn thanh toán cho nhân viên dựa trên giờ làm việc và doanh thu.

2.2 Các Lớp Phân Tích
NhânViên (Employee): Gửi yêu cầu thanh toán.
ThờiGian (Timecard): Cung cấp thông tin thời gian làm việc.
HệThốngLương (PayrollSystem): Quản lý quy trình thanh toán.
HóaĐơn (Invoice): Tạo và xác nhận hóa đơn thanh toán.
2.3 Biểu Đồ Tuần Tự
plantuml
Sao chép mã
@startuml
actor NhânViên
participant HệThốngLương
participant ThờiGian
participant HóaĐơn

NhânViên -> HệThốngLương: yêu cầuThanhToán()
HệThốngLương -> ThờiGian: lấyThôngTinThờiGian()
ThờiGian -> HệThốngLương: trảThôngTinThờiGian()
HệThốngLương -> HóaĐơn: tạoHóaĐơn()
HóaĐơn -> HệThốngLương: xác nhậnHóaĐơn()
HệThốngLương -> NhânViên: thôngBáoThanhToán()
@enduml
3. Ca Sử Dụng "Maintain Timecard"
3.1 Mô Tả
Ca sử dụng "Maintain Timecard" cho phép nhân viên ghi lại và duy trì thông tin thời gian làm việc.

3.2 Các Lớp Phân Tích
NhânViên (Employee): Gửi yêu cầu cập nhật thời gian làm việc.
ThờiGian (Timecard): Lưu trữ thông tin thời gian làm việc.
HệThốngLương (PayrollSystem): Quản lý và cập nhật thông tin thời gian.
XácNhận (Approval): Phê duyệt thông tin thời gian làm việc.
3.3 Biểu Đồ Tuần Tự
plantuml
Sao chép mã
@startuml
actor NhânViên
participant HệThốngLương
participant ThờiGian
participant XácNhận

NhânViên -> HệThốngLương: yêu cầuCậpNhậtThờiGian()
HệThốngLương -> ThờiGian: tạoThờiGian()
ThờiGian -> HệThốngLương: gửiThôngTinThờiGian()
HệThốngLương -> XácNhận: yêu cầuPhêDuyệt()
XácNhận -> HệThốngLương: trảTrạngTháiPhêDuyệt()
HệThốngLương -> NhânViên: thôngBáoTrạngTháiCậpNhật()
@enduml
4. Hợp Nhất Kết Quả Phân Tích
4.1 Sự Kết Hợp Giữa Hai Ca Sử Dụng
NhânViên: Trung tâm của cả hai ca sử dụng.
HệThốngLương: Lớp chính quản lý quy trình thanh toán và thông tin thời gian làm việc.
ThờiGian: Lưu trữ thông tin thời gian trong cả hai ca sử dụng.
HóaĐơn và XácNhận: Đảm bảo quy trình thanh toán và phê duyệt thông tin được thực hiện chính xác.
4.2 Đối Tượng và Quy Trình
Nhân viên tương tác với hệ thống để cập nhật thời gian làm việc và yêu cầu thanh toán. Hệ thống xử lý các yêu cầu này và thông báo trạng thái cho nhân viên.

5. Kết Luận
Tài liệu này đã hợp nhất phân tích cho hai ca sử dụng "Payment" và "Maintain Timecard", giúp cải thiện quy trình quản lý lương và thời gian làm việc tại Acme, Inc.

Nếu cần thêm thông tin hoặc chỉnh sửa, xin vui lòng cho biết!

