# KHUNG TRUYỀN MINI GETWAY

| OPCODE | Kiểu lệnh | mô tả |
| :---: | :--- | :--- | 
| 0xF0 | WIFI_SET_SSID | Lệnh cài đặt ssid wifi để kết nối |
| 0xF1 | WIFI_SET_SSID_STATUS | Trạng thái ssid đang kết nối |
| 0xF2 | WIFI_SET_PWD | Lệnh cài đặt mật khẩu wifi để kết nối |
| 0xF3 | WIFI_SET_PWD_STATUS | Trạng thái mật khẩu đang kết nối |
| 0xF4 | TOKEN_SET | lệnh set token cho việc kết nối lên cloud |
| 0xF5 | TOKEN_STATUS | trạng thái token |
| 0xF6 | USER_SET | Lệnh cài đặt user id cho việc kết nối lên cloud |
| 0xF7 | USER_STATUS | trạng thái user id đang kết nối |
| 0xDO | DFU_SET | Lệnh đưa mini getway vào DFU |
| 0xD1 | DFU_SET_UNACKNOWLEDGED | Lệnh đưa mini getway vào DFU |
| 0xD2 | DFU_STATUS | trạng thái vào DFU |

### 1. Message WIFI_SET_SSID

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| ssid | n | ssid cần set |

### 2. Message WIFI_SET_SSID_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| status | 1 | trạng thái set |

### 3. Message WIFI_SET_PW

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| ssid | n | password cần set |

### 4. Message WIFI_SET_PW_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| status | 1 | trạng thái set |

### 5. Message TOKEN_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| token | n | token cần setup |

### 6. Message TOKEN_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| status | 1 | trạng thái set token |

### 7. Message USER_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| user id | n | user id cần setup |

### 8. Message USER_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| status | 1 | trạng thái set user |


