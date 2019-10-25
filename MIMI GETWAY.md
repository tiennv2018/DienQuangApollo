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
| 0xF8 | URL_SET | Lệnh cài đặt địa chỉ server |
| 0xF9 | URL_STATUS | trạng thái cài đặt |
| 0xFA | KEY_SET | Lệnh cài đặt key |
| 0xFB | KEY_STATUS | trạng thái cài đặt |
| 0xFC | ENABLE_SETUP_SET | đưa esp vào chế độ setup |
| 0xFD | ENABLE_SETUP_STATUS | trạng thái cài đặt |
| 0xFE | WIFI_STATUS | trạng thái kết nối wifi |
| 0xFF | SERVER_STATUS | trạng thái kết nối server |
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

### 9. Message URL_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| url | n | url cần setup |

### 10. Message URL_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| status | 1 | trạng thái set url |

### 11. Message KEY_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| key | n | key cần setup |

### 12. Message KEY_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| status | 1 | trạng thái set key |

### 13. Message ENABLE_SETUP_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| cmd | 1 | 0/1 => enter/exit |

### 14. Message ENABLE_SETUP_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| status | 1 | trạng thái lệnh |

### 15. Message WIFI_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| status | 1 | trạng wifi |

### 16. Message SERVER_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| status | 1 | trạng thái kết nối đến server |

