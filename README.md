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
| 0xC4 | BRIGHTNESS_CALIBRATION_GET | Lệnh đọc về độ sáng đèn |
| 0xC5 | BRIGHTNESS_CALIBRATION_SET | Lệnh tăng hoặc giảm độ sáng đèn |
| 0xC6 | BRIGHTNESS_CALIBRATION_SET_UNACKNOWLEDGED | Lệnh tăng hoặc giảm độ sáng đèn  |
| 0xC7 | BRIGHTNESS_CALIBRATION_STATUS | Trạng thái độ sáng đèn |
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
| 0xD8 | POWER CONTROL GET | Đọc trạng thái nguồn |
| 0xD9 | POWER CONTROL SET | bật, tắt đảo trạng thái đèn |
| 0xDA | POWER CONTROL SET UNACKNOWLEDGED | bật, tắt đảo trạng thái đèn không xác nhận|
| 0xDB | POWER CONTROL STATUS | Trạng thái power |
| 0xDC | BRIGHTNESS GET | Đọc về độ sáng hiện tại |
| 0xDE | BRIGHTNESS SET | set độ sáng đến giá trị truyền xuống |
| 0xDF | BRIGHTNESS SET UNACKNOWLEDGED | set độ sáng đến giá trị truyền xuống không phản hồi |
| 0xC0 | BRIGHTNESS STATUS | Độ sáng hiện tại |
| 0xC1 | HSL GET | đọc về giá trị HSL hiện tại trong đèn |
| 0xC2 | HSL SET | set giá trị hsl cho đèn |
| 0xC3 | HSL SET UNACKNOWLEDGED | set giá trị hsl cho đèn, không phản hồi |
| 0xC4 | HSL STATUS | giá trị hsl hiện tại |
| 0xC5 | SATURATION GET | đọc về giá trị SATURATION hiện tại trong đèn |
| 0xC6 | SATURATION SET | set giá trị SATURATION cho đèn |
| 0xC7 | SATURATION SET UNACKNOWLEDGED | set giá trị SATURATION cho đèn, không phản hồi |
| 0xC8 | SATURATION STATUS | giá trị SATURATION hiện tại |
| 0xC9 | CTL GET | đọc về giá trị CTL hiện tại trong đèn |
| 0xCA | CTL SET | set giá trị CTL cho đèn |
| 0xCB | CTL SET UNACKNOWLEDGED | set giá trị CTL cho đèn, không phản hồi |
| 0xCC | CTL STATUS | giá trị CTL hiện tại |
| 0xCD | TEMPTURATE GET | đọc về giá trị TEMPTURATE hiện tại trong đèn |
| 0xCE | TEMPTURATE SET | set giá trị TEMPTURATE cho đèn |
| 0xCF | TEMPTURATE SET UNACKNOWLEDGED | set giá trị TEMPTURATE cho đèn, không phản hồi |
| 0xC0 | TEMPTURATE STATUS | giá trị TEMPTURATE hiện tại |
| 0xFE | VERSION_GET | Lệnh đọc về phiên bản firmware đèn hiện tại |
| 0xFF | VERSION_STATUS | phiên bản firmware hiện tại |
### 1. Message ACTIVITY_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message ACTIVITY_STATUS ```

### 2. Message ACTIVITY_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Activity | 1 | 1-> daylight, 2->HSL, 3->Effect |

``` Sau khi nhận lệnh này, đèn sẽ trả về message ACTIVITY_STATUS ```

### 3. Message ACTIVITY_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Activity | 1 | 1-> daylight, 2->HSL, 3->Effect |

### 4. Message ACTIVITY_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Value | 1 | 0->OFF, 1-> daylight, 2->HSL, 3->Effect |

### 5. Message BRIGHTNESS_CALIBRATION_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message BRIGHTNESS_CALIBRATION_SET_UNACKNOWLEDGED ```

### 6. Message BRIGHTNESS_CALIBRATION_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Type | 1 | nếu bằng 0-> giảm, bằng 1-> tăng|
| Value | 2 | giá trị cần tăng hoặc giảm |

``` Sau khi nhận lệnh này, đèn sẽ trả về message BRIGHTNESS_CALIBRATION_SET_UNACKNOWLEDGED ```

### 7. Message BRIGHTNESS_CALIBRATION_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Type | 1 | nếu bằng 0-> giảm, bằng 1-> tăng|
| Value | 2 | giá trị cần tăng hoặc giảm |

### 8. Message BRIGHTNESS_CALIBRATION_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Value | 2 | giá trị độ sáng hiện tại |

### 9. Message EFFECT_GET
``` Sau khi nhận lệnh này, đèn sẽ trả về message ACTIVITY_STATUS ```

### 10. Message EFFECT_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Lenght | 1 | Chiều dài của hiệu ứng tối đa là 12, chú ý chiều dài bao nhiêu thì dữ liệu hue, saturation, timer dài bấy nhiêu |
| type run | 1 | 0-> dimer, 1-> khong su dung dimer, 2-> dimer mau ngau nhien, 3-> khong su dung dimer, mau ngau nhien|
| lightness | 2 | độ sáng của hiệu ứng từ 0x0000 -> 0xFFFF |
| hue | 2 | giá trị hue cho màu đầu tiên của hiệu ứng, từ 0->360 |
| saturation | 2 |  giá trị saturation cho màu đầu tiên của hiệu ứng, từ 0->0xFFFF  |
| timer | 2 | thời gian duy trì màu đầu tiên, đơn vị miliseconds, sau thời gian này sẽ chuyển qua màu tiếp theo |

`` Chú ý: nếu len=1 thì như trên, còn nếu len=n thì sẽ lặp lại n-1 lần từ byte hue đến byte timer sau khung truyền trên, sau khi nhận lệnh này, đèn sẽ trả về message EFFECT_STATUS ``

### 11. Message EFFECT_SET_UNACKNOWLEDGED

 | Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Lenght | 1 | Chiều dài của hiệu ứng tối đa là 12, chú ý chiều dài bao nhiêu thì dữ liệu hue, saturation, timer dài bấy nhiêu |
| type run | 1 | 0-> dimer, 1-> khong su dung dimer, 2-> dimer mau ngau nhien, 3-> khong su dung dimer, mau ngau nhien |
| lightness | 2 | độ sáng của hiệu ứng từ 0x0000 -> 0xFFFF |
| hue | 2 | giá trị hue cho màu đầu tiên của hiệu ứng, từ 0->360 |
| saturation | 2 |  giá trị saturation cho màu đầu tiên của hiệu ứng, từ 0->0xFFFF  |
| timer | 2 | thời gian duy trì màu đầu tiên, đơn vị miliseconds, sau thời gian này sẽ chuyển qua màu tiếp theo |

`` Chú ý: nếu len=1 thì như trên, còn nếu len=n thì sẽ lặp lại n-1 lần từ byte hue đến byte timer sau khung truyền trên ``

### 12. Message EFFECT_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Lenght | 1 | Chiều dài của hiệu ứng tối đa là 12, chú ý chiều dài bao nhiêu thì dữ liệu hue, saturation, timer dài bấy nhiêu |
| type run | 1 | 0-> dimer, 1-> khong su dung dimer, 2-> dimer mau ngau nhien, 3-> khong su dung dimer, mau ngau nhien |
| lightness | 2 | độ sáng của hiệu ứng từ 0x0000 -> 0xFFFF |
| hue | 2 | giá trị hue cho màu đầu tiên của hiệu ứng, từ 0->360 |
| saturation | 2 |  giá trị saturation cho màu đầu tiên của hiệu ứng, từ 0->0xFFFF  |
| timer | 2 | thời gian duy trì màu đầu tiên, đơn vị miliseconds, sau thời gian này sẽ chuyển qua màu tiếp theo |

`` Chú ý: nếu len=1 thì như trên, còn nếu len=n thì sẽ lặp lại n-1 lần từ byte hue đến byte timer sau khung truyền trên ``

### 13. Message DEFAULT_EFFECT_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message DEFAULT_EFFECT_STATUS ```

### 14. Message DEFAULT_EFFECT_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| index | 1 | 0x00, 0x01, 0x02 hoac 0xFF, neu 0xFF thi se chay xoay vong tu 0->3 |
| TID | 1 | Transaction Identifier |

``` Trong đèn có lưu dữ liệu của 3 loại hiệu ứng, Mỗi lần nhận lệnh này sẽ chuyển các hiệu ứng có sẵn này và chạy ```

### 15. Message DEFAULT_EFFECT_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| index | 1 | 0x00, 0x01, 0x02 hoac 0xFF, neu 0xFF thi se chay xoay vong tu 0->3 |
| TID | 1 | Transaction Identifier |

### 16. Message DEFAULT_EFFECT_STATUS

``` tra ve Message EFFECT_STATUS ```

### 17. Message DFU_GET

``` luôn luôn trả về  Message DFU_STATUS với status = 0, vì khi đã vào dfu rồi thì thiết bị không còn connect proxy được nữa ```

### 18. Message DFU_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |

``` Sau khi nhận lệnh này, đèn sẽ trả về message DFU_STATUS ```

### 19. Message DFU_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |

### 20. Message DFU_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Status | 1 | Trạng thái thực hiện 0 hoặc 1 |

### 21. Message TEST_GET

``` Lệnh này đọc về trạng thái test đèn, trả về message TEST_STATUS ```

### 22. Message TEST_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| loop | 1 | số lần nhấp nháy, từ 0-> 255 |

``` Sau khi nhận lệnh này, đèn sẽ trả về message TEST_STATUS ```

### 23. Message TEST_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| loop | 1 | số lần nhấp nháy, từ 0-> 255 |

### 24. Message TEST_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| status | 1 | luôn luôn là 1, báo cho Client rằng đèn đã nhận được lệnh test light |

### 25. Message POWER CONTROL GET
``` Lệnh này đọc về trạng thái test đèn, trả về message 	POWER CONTROL STATUS ```

### 26. Message POWER CONTROL SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| cmd | 1 | 0/1/2 => off/on/toggle |

### 27. Message POWER CONTROL SET UNACKNOWLEDGED
``` tương tự như mesage POWER CONTROL SET nhưng không có trả lời từ thiết bị nhận ```

### 28. Message POWER CONTROL STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Value | 1 | 0->OFF, 1-> daylight, 2->HSL, 3->Effect |

### 29. Message BRIGHTNESS GET
``` trả về message BRIGHTNESS STATUS ```

### 30. Message BRIGHTNESS SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| lightness | 2 | giá trị từ 0->0xFFFF |

### 31. Message BRIGHTNESS SET UNACKNOWLEDGED
``` tương tự như mesage BRIGHTNESS SET nhưng không có trả lời từ thiết bị nhận ```

### 32. Message BRIGHTNESS STATUS
| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| lightness | 2 | giá trị từ 0->0xFFFF |

### 33. Message HSL GET
``` trả về message HSL STATUS ```

### 34. Message HSL SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| type | 1 | 0/1 => thay đổi màu kiểu dimer, thay đổi màu tức thì |
| hue | 2 | giá trị từ 0->0xFFFF tương ứng với 0->360 |
| saturation | 2 | giá trị từ 0->0xFFFF |
| lightness | 2 | giá trị từ 0->0xFFFF |

### 35. Message HSL SET UNACKNOWLEDGED
``` tương tự như mesage HSL SET nhưng không có trả lời từ thiết bị nhận ```

### 36. Message HSL STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| hue | 2 | giá trị từ 0->0xFFFF tương ứng với 0->360 |
| saturation | 2 | giá trị từ 0->0xFFFF |
| lightness | 2 | giá trị từ 0->0xFFFF |

### 37. Message SATURATION GET
``` trả về message SATURATION STATUS ```

### 38. Message SATURATION SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| type | 1 | 0/1 => thay đổi màu kiểu dimer, thay đổi màu tức thì |
| saturation | 2 | giá trị từ 0->0xFFFF |

### 39. Message SATURATION SET UNACKNOWLEDGED
``` tương tự như mesage SATURATION SET nhưng không có trả lời từ thiết bị nhận ```

### 40. Message SATURATION STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| saturation | 2 | giá trị từ 0->0xFFFF |

### 41. Message CTL GET
``` trả về message CTL STATUS ```

### 42. Message CTL SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| type | 1 | 0/1 => thay đổi màu kiểu dimer, thay đổi màu tức thì |
| Teampeturate | 2 | chính là nhiệt độ màu hiện tại của đèn |
| Lightness | 2 | giá trị từ 0->0xFFFF |

### 43. Message CTL SET UNACKNOWLEDGED
``` tương tự như mesage CTL SET nhưng không có trả lời từ thiết bị nhận ```

### 44. Message CTL STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Teampeturate | 2 | chính là nhiệt độ màu đèn hiện tại |
| Lightness | 2 | giá trị từ 0->0xFFFF |

### 45. Message TEMPTURATE GET
``` trả về message TEMPTURATE STATUS ```

### 46. Message TEMPTURATE SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| type | 1 | 0/1 => thay đổi màu kiểu dimer, thay đổi màu tức thì |
| Teampeturate | 2 | chính là nhiệt độ màu đèn hỗ trợ |

### 47. Message TEMPTURATE SET UNACKNOWLEDGED
``` tương tự như mesage TEMPTURATE SET nhưng không có trả lời từ thiết bị nhận ```

### 48. Message TEMPTURATE STATUS
| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Teampeturate | 2 | chính là nhiệt độ màu đèn hiện tại |

### 49. Message VESION_GET

``` Lệnh này đọc về  firmware đèn, trả về message VERSION_STATUS ```

### 50. Message VERSION_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| major | 1 | Chuỗi phiên bản chính, chữ số hàng chục định dạng text |
| major | 1 | Chuỗi phiên bản chính, 1 chữ số hàng đơn vị định dạng text |
| space | 1 | dấu . |
| minor | 1 | Chuỗi phiên bản phụ, chữ số hàng chục định dạng text |
| minor | 1 | Chuỗi phiên bản phụ, 1 chữ số hàng đơn vị định dạng text |
| space | 1 | dấu . |
| build | 1 | Chuỗi phiên bản cấu tạo. Đánh dấu sự khác nhau trong cùng 1 phiên bản phụ (hàng nghìn) định dạng text |
| build | 1 | Chuỗi phiên bản cấu tạo. Đánh dấu sự khác nhau trong cùng 1 phiên bản phụ (hàng trăm)  định dạng text |
| build | 1 | Chuỗi phiên bản cấu tạo. Đánh dấu sự khác nhau trong cùng 1 phiên bản phụ (hàng chục)  định dạng text |
| build | 1 | Chuỗi phiên bản cấu tạo. Đánh dấu sự khác nhau trong cùng 1 phiên bản phụ (hàng đơn vị) định dạng text |

```
Chỉ số major sẽ tăng mỗi khi:
- Có sự thay đổi lớn trong nhân hệ thống mà theo đó hệ thống mới có thể khác 1 phần hay hoàn toàn hệ thống cũ.
Chỉ số minor sẽ tăng mỗi khi:
- Có sự thay đổi phần core hệ thống mà không làm mất đi hoàn toàn tính tương thích trong cùng phiên bản chính.
Chỉ số build sẽ tăng mỗi khi:
- Có đóng gói gửi đi ra ngoài đội code nhằm các mục đích phát hành, thử nghiệm... (kể cả việc phát hành các phiên bản Closebeta, Openbeta, RC, Official version)
```

