# KHUNG TRUYỀN MINI LIGHT SENSOR

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


### 1. Message LUX_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message LUX_STATUS ```

### 2. Message LUX_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| value | 2 | giá trị cảm biến hiện tại đọc được |

### 3. Message RANGE_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message RANGE_STATUS ```

### 4. Message RANGE_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Range_Max | 2 | giá trị lớn nhất cảm biến đọc được |
| Range_Min | 2 | giá trị nhỏ nhất cảm biến đọc được |

### 5. Message SETLUX_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message SETLUX_STATUS ```

### 6. Message SETLUX_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Value | 2 | giá trị cần setup |

``` Sau khi nhận lệnh này, đèn sẽ trả về message SETLUX_STATUS ```

### 7. Message SETLUX_SET_UNKNOWELEDED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Value | 2 | giá trị cần setup |

``` Sau khi nhận lệnh này không có dữ liệu trả về ```

### 8. Message SETLUX_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Value | 2 | giá trị cần setup |

### 9. Message TOLERANCE_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message TOLERANCE_STATUS ```

### 9. Message TOLERANCE_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| value | 2 | sai số cần cài đặt |

``` Sau khi nhận lệnh này, đèn sẽ trả về message TOLERANCE_STATUS ```

### 10. Message TOLERANCE_SET_UNKNOWELEDED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| value | 2 | sai số cần cài đặt |

``` Sau khi nhận lệnh này không có dữ liệu trả về ```

### 11. Message TOLERANCE_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| value | 2 | sai số hiện tại của thiết bị |

### 12. Message ENABLE_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message ENABLE_STATUS ```

### 13. Message ENABLE_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| enable | 1 | cho phép (1) hoặc không cho phép (0) điều khiển |

``` Sau khi nhận lệnh này, đèn sẽ trả về message ENABLE_STATUS ```

### 14. Message ENABLE_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| enable | 1 | cho phép (1) hoặc không cho phép (0) điều khiển |

``` Sau khi nhận lệnh này không có dữ liệu trả về ```

### 15. Message ENABLE_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| enable | 1 | đang cho phép (1), không cho phép (0) điều khiển |

### 16. Message DFU_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |

``` Sau khi nhận lệnh này, đèn sẽ trả về message DFU_STATUS ```

### 17. Message DFU_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |

``` Sau khi nhận lệnh này không có dữ liệu trả về ```

### 18. Message DFU_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| enable | 1 | luôn trả về 1 khi nhận lệnh này |

