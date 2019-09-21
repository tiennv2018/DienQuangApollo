# KHUNG TRUYỀN MINI GETWAY

| OPCODE | Kiểu lệnh | mô tả |
| :---: | :--- | :--- | 
| 0xF0 | WIFI_GET | Lệnh đọc về ssid và mật khẩu wifi đang kết nối |
| 0xF1 | WIFI_SET | Lệnh cài đặt ssid và mật khẩu wifi để kết nối |
| 0xF2 | WIFI_SET_UNACKNOWLEDGED | Lệnh cài đặt ssid và mật khẩu wifi để kết nối  |
| 0xF3 | WIFI_STATUS | Trạng thái ssid và mật khẩu đang kết nối |
| 0xF4 | TOKEN_GET | lệnh đọc về token đang kết nối lên cloud |
| 0xF5 | TOKEN_SET | lệnh set token cho việc kết nối lên cloud |
| 0xF6 | TOKEN_SET_UNACKNOWLEDGED | lệnh set token cho việc kết nối lên cloud |
| 0xF7 | TOKEN_STATUS | trạng thái token |
| 0xF8 | USER_GET | Lệnh đọc về user id đang kết nối lên cloud |
| 0xF9 | USER_SET | Lệnh cài đặt user id cho việc kết nối lên cloud |
| 0xFA | USER_SET_UNACKNOWLEDGED | Lệnh cài đặt user id cho việc kết nối lên cloud |
| 0xFB | USER_STATUS | trạng thái user id đang kết nối |
| 0xD0 | DFU_SET | Lệnh đưa mini getway vào DFU |
| 0xD1 | DFU_SET_UNACKNOWLEDGED | Lệnh đưa mini getway vào DFU |
| 0xD2 | DFU_STATUS | trạng thái vào DFU |
| 0xFE | VERSION_GET | Lệnh đọc về phiên bản firmware đèn hiện tại |
| 0xFF | VERSION_STATUS | phiên bản firmware hiện tại |

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
| ssid | n | ssid cần kết nối |

### 7. Message TOKEN_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| ssid length | 1 | chiều dài của ssid |
| ssid | n | ssid cần kết nối |
| password | m | mật khẩu tương ứng với ssid |

### 8. Message TOKEN_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| ssid length | 1 | chiều dài của ssid |
| ssid | n | ssid cần kết nối |
| password | m | mật khẩu tương ứng với ssid |

