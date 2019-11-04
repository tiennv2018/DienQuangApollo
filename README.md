# Apollo vendor model protocol

* Opcode define

| OPCODE | type  | content |
| :---: | :--- | :--- | 
| 0xC0 | ACTIVITY_GET | get current model |
| 0xC1 | ACTIVITY_SET | set run model: 1-> daylight, 2->HSL, 3->Color loop |
| 0xC2 | ACTIVITY_SET_UNACKNOWLEDGED | set run model: 1-> daylight, 2->HSL, 3->Color loop  |
| 0xC3 | ACTIVITY_STATUS | model status |
| 0xC8 | EFFECT_GET | get data of color loop |
| 0xC9 | EFFECT_SET | set data of color loop|
| 0xCA | EFFECT_SET_UNACKNOWLEDGED | set data of color loop |
| 0xCB | EFFECT_STATUS | color loop status |
| 0xCC | DEFAULT_EFFECT_GET | get default color loop |
| 0xCD | DEFAULT_EFFECT_SET | Set default color loop |
| 0xCE | DEFAULT_EFFECT_SET_UNACKNOWLEDGED | Set default color loop |
| 0xCF | DEFAULT_EFFECT_STATUS | default color loop status |
| 0xD0 | DFU_SET | Enter DFU |
| 0xD1 | DFU_SET_UNACKNOWLEDGED | Enter DFU  |
| 0xD2 | DFU_STATUS | dfu status |
| 0xD3 | TEST_SET | Set Blinking test|
| 0xD4 | TEST_SET_UNACKNOWLEDGED | Set Blinking test |
| 0xD5 | TEST_STATUS | Blinking test status |
| 0xD6 | POWER CONTROL GET | Get status current status light |
| 0xD7 | POWER CONTROL SET | Set model light: 0/1/2 => off/on/toggle |
| 0xD8 | POWER CONTROL SET UNACKNOWLEDGED | Set model light: 0/1/2 => off/on/toggle |
| 0xD9 | POWER CONTROL STATUS | status light  |
| 0xDA | BRIGHTNESS GET | Get brightness |
| 0xDB | BRIGHTNESS SET | set brightness |
| 0xDC | BRIGHTNESS SET UNACKNOWLEDGED | set brightness |
| 0xDD | BRIGHTNESS STATUS | brightness status |
| 0xDE | HSL GET | get HSL |
| 0xDF | HSL SET | set HSL |
| 0xE0 | HSL SET UNACKNOWLEDGED | set HSL |
| 0xE1 | HSL STATUS | HSL status |
| 0xE2 | SATURATION GET | get saturation |
| 0xE3 | SATURATION SET | set saturation |
| 0xE4 | SATURATION SET UNACKNOWLEDGED | set saturation |
| 0xE5 | SATURATION STATUS | saturation status |
| 0xE6 | CTL GET | Get CTL |
| 0xE7 | CTL SET | set CTL |
| 0xE8 | CTL SET UNACKNOWLEDGED | set CTL |
| 0xE9 | CTL STATUS | CTL status |
| 0xEA | TEMPTURATE GET | Get color temperature |
| 0xEB | TEMPTURATE SET | Set color temperature |
| 0xEC | TEMPTURATE SET UNACKNOWLEDGED | Set color temperature  |
| 0xED | TEMPTURATE STATUS |  Color temperature status |
| 0xEE | VENDOR_SERVER_OPCODE_TEMPTURATE_RANGE_GET | Get color temperature range |
| 0xEF | VENDOR_SERVER_OPCODE_TEMPTURATE_RANGE_STATUS | Color temperature range status |

### 1. Message ACTIVITY_GET

``` The response to the ACTIVITY_GET is a ACTIVITY_STATUS. There are no parameters for this message. ```

### 2. Message ACTIVITY_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Activity | 1 | 0x01-> daylight, 0x02->HSL, 0x03->Effect |

``` The response to the ACTIVITY_SET is a ACTIVITY_STATUS. ```

### 3. Message ACTIVITY_SET_UNACKNOWLEDGED

``` The Light ACTIVITY_SET_UNACKNOWLEDGED is an unacknowledged message used to set the Activity Actual state of an element ```

### 4. Message ACTIVITY_STATUS

``` The ACTIVITY_STATUS is an unacknowledged message used to report the Activity Actual state of an element  ```

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Value | 1 | 0->OFF, 1-> daylight, 2->HSL, 3->Effect |

### 9. Message EFFECT_GET
``` The response to the EFFECT_GET is a EFFECT_STATUS. There are no parameters for this message. ```

### 10. Message EFFECT_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Lenght | 1 | length of color loop data  |
| type run | 1 | 0-> dimer, 1-> not dimer, 2-> dimer and random, 3-> not dimer and random |
| hue | 2 | hue of data color loop segment 0, from 0x0000 to 0xFFFF |
| saturation | 2 |  saturation of data color loop segment 0, from 0x0000 to 0xFFFF  |
| lightness | 2 | lightness of data color loop segment 0, from 0x0000 to 0xFFFF |
| timer | 2 | delay of data color loop segment 0, from 0x0000 to 0xFFFF |
| hue | 2 | hue of data color loop segment 1, from 0x0000 to 0xFFFF |
| saturation | 2 |  saturation of data color loop segment 1, from 0x0000 to 0xFFFF  |
| lightness | 2 | lightness of data color loop segment 1, from 0x0000 to 0xFFFF |
| timer | 2 | delay of data color loop segment 1, from 0x0000 to 0xFFFF |
| ... | ... | ... |
| hue | 2 | hue of data color loop segment n, from 0x0000 to 0xFFFF |
| saturation | 2 |  saturation of data color loop segment n, from 0x0000 to 0xFFFF  |
| lightness | 2 | lightness of data color loop segment n, from 0x0000 to 0xFFFF |
| timer | 2 | delay of data color loop segment n, from 0x0000 to 0xFFFF |

``` example: enter color loop model with red color and green color ```

| byte | tid | Length | type run | lb_hue | hb_hue | lb_saturation | hb_saturation | lb_lightness | hb_lightness | lb_timer | hb_timer | lb_hue | hb_hue | lb_saturation | hb_saturation | lb_lightness | hb_lightness | lb_timer | hb_timer | 
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| giá trị | 0x00 | 0x02 | 0x00 | 0x00 | 0x00 | 0xFF | 0xFF | 0x00 | 0x80 | 0xE8 | 0x03 | 0x55 | 0x55 | 0xFF | 0xFF | 0x00 | 0x80 | 0xD0 | 0x07 | 

``` note: lenght length is 2 for red and green  ```


### 11. Message EFFECT_SET_UNACKNOWLEDGED

``` The Light EFFECT_SET_UNACKNOWLEDGED is an unacknowledged message used to set the data of color loop Actual state of an element ```

### 12. Message EFFECT_STATUS

``` The EFFECT_STATUS is an unacknowledged message used to report the data of color loop Actual state of an element  ```

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
| TID | 1 | Transaction Identifier |
| index | 1 | 0x00, 0x01, 0x02 hoac 0xFF, neu 0xFF thi se chay xoay vong tu 0->3 |

``` Trong đèn có lưu dữ liệu của 3 loại hiệu ứng, Mỗi lần nhận lệnh này sẽ chuyển các hiệu ứng có sẵn này và chạy ```

### 15. Message DEFAULT_EFFECT_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| index | 1 | 0x00, 0x01, 0x02, 0x03 tương ứng với rgb không nhuyễn, rgb nhuyễn, random không nhuyễn, random nhuyễn, hoặc 0xFF cho remote |

### 16. Message DEFAULT_EFFECT_STATUS

``` tra ve Message EFFECT_STATUS ```

### 17. Message DFU_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |

``` Sau khi nhận lệnh này, đèn sẽ trả về message DFU_STATUS ```

### 18. Message DFU_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |

### 19. Message DFU_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Status | 1 | Trạng thái thực hiện 0 hoặc 1 |

### 20. Message TEST_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| loop | 1 | số lần nhấp nháy, từ 0-> 255 |

``` Sau khi nhận lệnh này, đèn sẽ trả về message TEST_STATUS ```

### 21. Message TEST_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| loop | 1 | số lần nhấp nháy, từ 0-> 255 |

### 22. Message TEST_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| status | 1 | luôn luôn là 1, báo cho Client rằng đèn đã nhận được lệnh test light |

### 23. Message POWER CONTROL GET
``` Lệnh này đọc về trạng thái test đèn, trả về message 	POWER CONTROL STATUS ```

### 24. Message POWER CONTROL SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| cmd | 1 | 0/1/2 => off/on/toggle |

### 25. Message POWER CONTROL SET UNACKNOWLEDGED
``` tương tự như mesage POWER CONTROL SET nhưng không có trả lời từ thiết bị nhận ```

### 26. Message POWER CONTROL STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Value | 1 | 0->OFF, 1-> ON |

### 27. Message BRIGHTNESS GET
``` trả về message BRIGHTNESS STATUS ```

### 28. Message BRIGHTNESS SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| lightness | 2 | giá trị từ 0->0xFFFF |

### 29. Message BRIGHTNESS SET UNACKNOWLEDGED
``` tương tự như mesage BRIGHTNESS SET nhưng không có trả lời từ thiết bị nhận ```

### 30. Message BRIGHTNESS STATUS
| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| lightness | 2 | giá trị từ 0->0xFFFF |

### 31. Message HSL GET
``` trả về message HSL STATUS ```

### 32. Message HSL SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| type | 1 | 0/1 => thay đổi màu kiểu dimer, thay đổi màu tức thì |
| hue | 2 | giá trị từ 0->0xFFFF tương ứng với 0->360 |
| saturation | 2 | giá trị từ 0->0xFFFF |
| lightness | 2 | giá trị từ 0->0xFFFF |

### 33. Message HSL SET UNACKNOWLEDGED
``` tương tự như mesage HSL SET nhưng không có trả lời từ thiết bị nhận ```

### 34. Message HSL STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| hue | 2 | giá trị từ 0->0xFFFF tương ứng với 0->360 |
| saturation | 2 | giá trị từ 0->0xFFFF |
| lightness | 2 | giá trị từ 0->0xFFFF |

### 35. Message SATURATION GET
``` trả về message SATURATION STATUS ```

### 36. Message SATURATION SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| type | 1 | 0/1 => thay đổi màu kiểu dimer, thay đổi màu tức thì |
| saturation | 2 | giá trị từ 0->0xFFFF |

### 37. Message SATURATION SET UNACKNOWLEDGED
``` tương tự như mesage SATURATION SET nhưng không có trả lời từ thiết bị nhận ```

### 38. Message SATURATION STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| saturation | 2 | giá trị từ 0->0xFFFF |

### 39. Message CTL GET
``` trả về message CTL STATUS ```

### 40. Message CTL SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| Teampeturate | 2 | chính là nhiệt độ màu hiện tại của đèn |
| Lightness | 2 | giá trị từ 0->0xFFFF |

### 41. Message CTL SET UNACKNOWLEDGED
``` tương tự như mesage CTL SET nhưng không có trả lời từ thiết bị nhận ```

### 42. Message CTL STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Teampeturate | 2 | chính là nhiệt độ màu đèn hiện tại |
| Lightness | 2 | giá trị từ 0->0xFFFF |

### 43. Message TEMPTURATE GET
``` trả về message TEMPTURATE STATUS ```

### 44. Message TEMPTURATE SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | tid cho message này |
| Teampeturate | 2 | chính là nhiệt độ màu đèn hỗ trợ |

### 45. Message TEMPTURATE SET UNACKNOWLEDGED
``` tương tự như mesage TEMPTURATE SET nhưng không có trả lời từ thiết bị nhận ```

### 46. Message TEMPTURATE STATUS
| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Teampeturate | 2 | chính là nhiệt độ màu đèn hiện tại |



### 47. Message TEMPTURATE RANGE GET
``` trả về message TEMPTURATE STATUS ```

### 48. Message TEMPTURATE RANGE STATUS
| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Range_Max | 2 | giá trị nhiệt độ màu cao nhất đèn hỗ trợ |
| Range_Min | 2 | giá trị nhiệt độ màu thấp nhất đèn hỗ trợ |

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

