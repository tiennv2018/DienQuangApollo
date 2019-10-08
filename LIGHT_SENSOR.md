# KHUNG TRUYỀN MINI GETWAY

| OPCODE | Kiểu lệnh | mô tả |
| :---: | :--- | :--- | 
| 0xC0 | LUX_GET | Lệnh đọc về giá trị cảm biến hiện tại |
| 0xC1 | LUX_STATUS | Lệnh trả về giá trị cảm biên hiện tại |
| 0xC2 | RANGE_GET | lệnh đọc về range giá trị cảm biến hỗ trợ  |
| 0xC3 | RANGE_STATUS | Lệnh trả về range giá trị cảm biến hỗ trợ |
| 0xC4 | SETLUX_GET | lệnh đọc về giá trị đã setup cho cảm biến  |
| 0xC5 | SETLUX_SET | lệnh cài đặt giá trị cho cảm biến  |
| 0xC6 | SETLUX_SET_UNKNOWELEDED | lệnh cài đặt giá trị cho cảm biến |
| 0xC7 | SETLUX_STATUS | lệnh trả về giá trị đã setup |
| 0xC8 | TOLERANCE_GET | lệnh đọc về giá trị setup cho giá trị sai số mới gửi lệnh điều khiển |
| 0xC9 | TOLERANCE_SET | cài đặt giá trị setup cho giá trị sai số mới gửi lệnh điều khiển |
| 0xCA | TOLERANCE_SET_UNKNOWELEDED | cài đặt giá trị setup cho giá trị sai số mới gửi lệnh điều khiển |
| 0xCB | TOLERANCE_STATUS | trả về giá trị setup cho giá trị sai số mới gửi lệnh điều khiển |
| 0xCD | ENABLE_GET | đọc về xem có cho phép điều khiển không |
| 0xCE | ENABLE_SET | cài đặt việc cho phép điều khiển không |
| 0xCF | ENABLE_SET_UNKNOWELEDED | cài đặt việc cho phép điều khiển không |
| 0xD3 | ENABLE_STATUS | trả về trạng thái có cho phép điều khiển không |
| 0xD0 | DFU_SET | Lệnh đưa thiết bị vào DFU |
| 0xD1 | DFU_SET_UNKNOWELEDED | Lệnh đưa thiết bị vào DFU |
| 0xD2 | DFU_STATUS | Trạng thái vào DFU |


### 1. Message WIFI_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message WIFI_STATUS ```

### 2. Message WIFI_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| ssid length | 1 | chiều dài của ssid |
| ssid | n | ssid cần kết nối |
| password | m | mật khẩu tương ứng với ssid |

### 3. Message WIFI_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| ssid length | 1 | chiều dài của ssid |
| ssid | n | ssid cần kết nối |
| password | m | mật khẩu tương ứng với ssid |

### 4. Message WIFI_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| ssid length | 1 | chiều dài của ssid |
| ssid | n | ssid cần kết nối |
| password | m | mật khẩu tương ứng với ssid |

### 5. Message TOKEN_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message TOKEN_STATUS ```

### 6. Message TOKEN_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| token | n | token cần setup |

### 7. Message TOKEN_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| token | n | token cần setup |

### 8. Message TOKEN_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| token | n | token hiện tại |

### 9. Message USER_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message TOKEN_STATUS ```

### 10. Message USER_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| user id | n | user id cần setup |

### 11. Message USER_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| user id | n | user id cần setup |

### 12. Message USER_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| user id | n | user id hiện tại |


