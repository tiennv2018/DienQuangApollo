# KHUNG TRUYỀN ĐIỀU KHIỂN ĐÈN APOLLO V3 THEO CHUẨN SIG MESH

## 1. Protocol điều khiển theo chuẩn SIG MESH với model HSL và CTL

* tham khảo tài liệu SIG MESH theo link http://www.mediafire.com/file/1w1zl6zi04vb7j2/Bluetooth_SIG_307.pdf/file ở line 307 thể hiện ID của các Model và line 301 thể hiện các OPCODE. định dạng message xem từ mục lục rồi click đến mục tương ứng.

## 2. Protocol điều khiển đèn theo chuẩn điện quang với Vendor Model (SIG MESH)
* Điện quang sử dụng chip Bluetooth Nordic nên Vendor Model sẽ có ID là 0x00590000 (trong đó 4 số đầu là id của chip Nordic đã được đăng kí, còn 4 số sau là điện quang tùy chọn để sử dụng)

* Bảng mã OPCODE theo chuẩn điện quang trong model Vendor Mode
| OPCODE | Kiểu lệnh | mô tả |unacknowledged
| :---: | :--- | :--- |
| 0xC0 | GET | Lệnh đọc về trạng thái đèn |
| 0xC1 | SET | Lệnh đảo trạng thái đèn và đèn sẽ trả lời khi nhận được lệnh này |
| 0xC2 | SET UNACKNOWLEDGED | Lệnh đảo trạng thái đèn |
| 0xC3 | STATUS | Trả về trạng thái của đèn, tương tự lệnh GET |
| 0xC4 | SET | Lệnh giảm độ sáng đèn so với độ sáng hiện tại,  đèn trả lời lại khi nhận được lệnh |
| 0xC5 | SET UNACKNOWLEDGED | Lệnh giảm độ sáng đèn so với độ sáng hiện tại |
| 0xC3 | STATUS | Trả về độ sáng đèn so với độ sáng hiện tại |

| 0xC6 | SET | Lệnh tăng độ sáng đèn so với độ sáng hiện tại,  đèn trả lời lại khi nhận được lệnh |
| 0xC7 | SET UNACKNOWLEDGED | Lệnh tăng độ sáng đèn so với độ sáng hiện tại |

| 0xC6 | SET | Lệnh chuyển chế độ tự động |
| 0xC7 | SET UNACKNOWLEDGED | lệnh chuyển chế độ tự động v |

| 0xC4 |  | Lệnh giảm độ sáng đèn so với độ sáng hiện tại,  đèn trả lời lại khi nhận được lệnh |
| 0xC4 | SET UNACKNOWLEDGED | Lệnh giảm độ sáng đèn so với độ sáng hiện tại |
