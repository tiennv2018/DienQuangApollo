# KHUNG TRUYỀN ĐIỀU KHIỂN ĐÈN APOLLO V3 THEO CHUẨN SIG MESH

## 1. Protocol điều khiển theo chuẩn SIG MESH với model HSL và CTL

* tham khảo tài liệu SIG MESH theo link http://www.mediafire.com/file/1w1zl6zi04vb7j2/Bluetooth_SIG_307.pdf/file ở line 307 thể hiện ID của các Model và line 301 thể hiện các OPCODE. định dạng message xem từ mục lục rồi click đến mục tương ứng.

## 2. Protocol điều khiển đèn theo chuẩn điện quang với Vendor Model (SIG MESH)
* Điện quang sử dụng chip Bluetooth Nordic nên Vendor Model sẽ có ID là 0x00590000 (trong đó 4 số đầu là id của chip Nordic đã được đăng kí, còn 4 số sau là điện quang tùy chọn để sử dụng)

* Bảng mã OPCODE theo chuẩn điện quang trong model Vendor Mode

| OPCODE | Kiểu lệnh | mô tả |
| :---: | :--- | :--- | 
| 0xC0 | ACTIVITY_GET | Lệnh đọc về trạng thái đèn |
| 0xC1 | ACTIVITY_SET | Lệnh set chế độ đèn, daylight, warm white |
| 0xC2 | ACTIVITY_SET_UNACKNOWLEDGED | Lệnh set chế độ đèn, daylight, warm white  |
| 0xC3 | ACTIVITY_STATUS | Trạng thái activity |
| 0xC4 | BRIGHTNESS_GET | Lệnh đọc về độ sáng đèn |
| 0xC5 | BRIGHTNESS_SET | Lệnh tăng hoặc giảm độ sáng đèn |
| 0xC6 | BRIGHTNESS_SET_UNACKNOWLEDGED | Lệnh tăng hoặc giảm độ sáng đèn  |
| 0xC7 | BRIGHTNESS_STATUS | Trạng thái độ sáng đèn |
| 0xC8 | EFFECT_GET | Đọc về hiệu ứng đang chạy |
| 0xC9 | EFFECT_SET | Lệnh set hiệu ứng |
| 0xCA | EFFECT_SET_UNACKNOWLEDGED | Lệnh set hiệu ứng |
| 0xCB | EFFECT_STATUS | Trạng thái hiệu ứng đang set |
| 0xCC | DEFAULT_EFFECT_GET | Đọc về hiệu ứng mặc định đang chạy |
| 0xCD | DEFAULT_EFFECT_SET | Set hiệu ứng chạy |
| 0xCE | DEFAULT_EFFECT_SET_UNACKNOWLEDGED | Set hiệu ứng chạy |
| 0xCF | DEFAULT_EFFECT_STATUS | Trạng thái hiệu ứng đang set |
| 0xD0 | DFU_GET | Lệnh đọc chế độ dfu |
| 0xD1 | DFU_SET | Lệnh set đèn vào chế độ DFU |
| 0xD2 | DFU_SET_UNACKNOWLEDGED | Lệnh set đèn vào chế độ DFU  |
| 0xD3 | DFU_STATUS | Trạng thái dfu |
| 0xD4 | TEST_GET | Lệnh đọc về trạng thái đèn |
| 0xD5 | TEST_SET | Lệnh test đèn|
| 0xD6 | TEST_SET_UNACKNOWLEDGED | Lệnh test đèn  |
| 0xD7 | TEST_STATUS | Trạng thái test đèn |

### 1. Message ACTIVITY_GET


### 2. Message ACTIVITY_SET


### 3. Message ACTIVITY_SET_UNACKNOWLEDGED


### 4. Message ACTIVITY_STATUS


### 5. Message BRIGHTNESS_GET


### 6. Message BRIGHTNESS_SET


### 7. Message BRIGHTNESS_SET_UNACKNOWLEDGED


### 8. Message BRIGHTNESS_STATUS


### 9. Message EFFECT_GET


### 10. Message EFFECT_SET


### 11. Message EFFECT_SET_UNACKNOWLEDGED


### 12. Message EFFECT_STATUS


### 13. Message DEFAULT_EFFECT_GET


### 14. Message DEFAULT_EFFECT_SET


### 15. Message DEFAULT_EFFECT_SET_UNACKNOWLEDGED


### 16. Message DEFAULT_EFFECT_STATUS


### 1. Message DFU_GET


### 2. Message DFU_SET


### 3. Message DFU_SET_UNACKNOWLEDGED


### 4. Message DFU_STATUS


### 5. Message TEST_GET


### 6. Message TEST_SET


### 7. Message TEST_SET_UNACKNOWLEDGED


### 8. Message TEST_STATUS
