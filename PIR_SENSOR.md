
# KHUNG TRUYỀN PIR SENSOR

| OPCODE | Kiểu lệnh | mô tả |
| :---: | :--- | :--- | 
| 0xC0 | DELAY_GET | lệnh đọc về giá trị delay đã setup cho cảm biến  |
| 0xC1 | DELAY_SET | lệnh cài đặt giá trị delay cho cảm biến  |
| 0xC2 | DELAY_SET_UNKNOWELEDED | lệnh cài đặt giá trị delay cho cảm biến |
| 0xC3 | DELAY_STATUS | lệnh trả về giá trị delay đã setup |
| 0xC4 | LEVEL_GET | lệnh đọc về giá trị level hight và level low cho việc dimming |
| 0xC5 | LEVEL_SET | lệnh cài đặt giá trị level hight và level low cho việc dimming |
| 0xC6 | LEVEL_SET_UNKNOWELEDED | lệnh cài đặt giá trị level hight và level low cho việc dimming |
| 0xC7 | LEVEL_STATUS | trả về giá trị level hight và level low cho việc dimming |
| 0xC8 | STATUS_GET | lệnh đọc về trạng thái pir hiện tại |
| 0xC9 | STATUS_STATUS | trả về trạng thái pir hiện tại |
| 0xD0 | DFU_SET | Lệnh đưa thiết bị vào DFU |
| 0xD1 | DFU_SET_UNKNOWELEDED | Lệnh đưa thiết bị vào DFU |
| 0xD2 | DFU_STATUS | Trạng thái vào DFU |

### 1. Message DELAY_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message DELAY_STATUS ```

### 2. Message DELAY_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Value | 2 | giá trị cần setup (x100ms), ví dụ 10-> 10x100 = 1s |

``` Sau khi nhận lệnh này, đèn sẽ trả về message DELAY_STATUS ```

### 3. Message DELAY_SET_UNKNOWELEDED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| Value | 2 | giá trị cần setup (x100ms), ví dụ 10-> 10x100 = 1s |

``` Sau khi nhận lệnh này không có dữ liệu trả về ```

### 4. Message DELAY_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| Value | 2 | giá trị delay (x100ms), ví dụ 10-> 10x100 = 1s |

### 5. Message LEVEL_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message LEVEL_STATUS ```

### 6. Message LEVEL_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| LOW | 2 | mức thấp dimming (0->0xFFFF) |
| HIGH | 2 | mức cao dimming (0->0xFFFF) |

``` Sau khi nhận lệnh này, đèn sẽ trả về message LEVEL_STATUS ```

### 7. Message LEVEL_SET_UNKNOWELEDED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |
| LOW | 2 | mức thấp dimming (0->0xFFFF) |
| HIGH | 2 | mức cao dimming (0->0xFFFF) |

``` Sau khi nhận lệnh này không có dữ liệu trả về ```

### 8. Message LEVEL_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| LOW | 2 | mức thấp dimming (0->0xFFFF) |
| HIGH | 2 | mức cao dimming (0->0xFFFF) |

### 9. Message STATUS_GET

``` Sau khi nhận lệnh này, đèn sẽ trả về message STATUS_STATUS ```

### 10. Message STATUS_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| LOW | 2 | 0-> Not active, 1-> actived |

### 11. Message DFU_SET

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |

``` Sau khi nhận lệnh này, đèn sẽ trả về message DFU_STATUS ```

### 12. Message DFU_SET_UNACKNOWLEDGED

| Field | Size (octets) | Notes |
| :--- | :--- | :--- | 
| TID | 1 | Transaction Identifier |

``` Sau khi nhận lệnh này không có dữ liệu trả về ```

### 13. Message DFU_STATUS

| Field | Size (octets) | Notes |
| :--- | :--- | :--- |
| enable | 1 | luôn trả về 1 khi nhận lệnh này |

