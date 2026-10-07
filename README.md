# Bài 4: Điều khiển 1 LED bằng OneButton

## Chức năng
- **Nhấn 1 lần (Single Click):** Bật hoặc tắt LED
- **Nhấn đúp (Double Click):** Chuyển sang chế độ nháy LED liên tục

## Linh kiện & Nối dây
- **Board:** ESP32 Devkit V1
- **LED ngoài:** Cực dương cắm vào chân D4, cực âm nối qua trở 1k xuống GND
- **Nút nhấn:** 1 chân cắm vào D23, chân còn lại nối GND (trong code đã dùng `INPUT_PULLUP`)

# Bài 5: Mở rộng 1 nút nhấn điều khiển 2 LED

Chỉ với 1 nút nhấn, ta có thể điều khiển độc lập được 2 đèn LED (1 cái có sẵn trên board, 1 cái cắm ngoài)

## Cách hoạt động
- **Nhấn đúp (Double Click):** Đổi qua lại quyền điều khiển giữa LED 1 và LED 2
- **Nhấn 1 lần (Single Click):** Bật/tắt LED đang được chọn
- **Nhấn giữ (Long Press):** LED đang được chọn sẽ nháy liên tục (200ms/lần). Khi nhả thả ra, LED tự quay về trạng thái lúc trước khi bấm giữ

## Sơ đồ đấu nối phần cứng
- **LED 1 (Built-in):** Dùng LED tích hợp trên board ESP32
- **LED 2 (Gắn ngoài):** Chân dương nối vào D4, chân âm nối qua điện trở 1k xuống GND
- **Nút nhấn:** 1 chân nối vào D23, chân kia nối GND
