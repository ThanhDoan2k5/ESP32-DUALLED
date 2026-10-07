# Điều khiển LED bằng thư viện OneButton

Dự án này sử dụng thư viện `OneButton` trên nền tảng PlatformIO để điều khiển một đèn LED thông qua nút nhấn với các thao tác khác nhau, thay thế cho hàm `delay()` truyền thống.

## Tính năng
- **Single Click (Nhấn 1 lần):** Bật hoặc tắt đèn LED (Toggle ON/OFF).
- **Double Click (Nhấn đúp):** Chuyển đổi giữa chế độ sáng tĩnh và chế độ nhấp nháy liên tục (Blink).

## Yêu cầu phần cứng
- 1 x ESP32 Devkit V1 (30 chân)
- 1 x Đèn LED
- 1 x Điện trở 1kΩ
- 1 x Nút nhấn (Push button)

## Sơ đồ đấu nối
- **LED:** Cực dương nối với chân GPIO 4 (D4) của ESP32, cực âm nối qua điện trở 1kΩ xuống chân GND.
- **Nút nhấn:** Một chân nối với GPIO 23 (D23), chân cùng phía còn lại nối xuống GND (Mạch sử dụng điện trở kéo lên nội bộ `INPUT_PULLUP`).

## Cấu hình phần mềm
- Môi trường: PlatformIO IDE (VS Code).
- Framework: Arduino.
- Thư viện phụ thuộc: `mathertel/OneButton` (được tự động quản lý qua `platformio.ini`).

# Hệ thống điều khiển 2 LED độc lập bằng 1 Nút nhấn

Dự án mở rộng khả năng điều khiển đa nhiệm, cho phép quản lý trạng thái của 2 đèn LED độc lập chỉ bằng một nút nhấn duy nhất trên bo mạch ESP32 thông qua thư viện OneButton.

## Tính năng cốt lõi
- **Double Click (Nhấn đúp):** Chuyển đổi quyền điều khiển qua lại giữa LED 1 (Built-in) và LED 2 (Gắn ngoài).
- **Single Click (Nhấn 1 lần):** Bật hoặc tắt (Toggle ON/OFF) trạng thái của đèn LED đang được chọn.
- **Long Press (Nhấn giữ):** Đèn LED đang được chọn sẽ nhấp nháy liên tục với chu kỳ 200ms bằng thuật toán non-blocking. Khi nhả nút, LED tự động trở về trạng thái sáng/tắt tĩnh ban đầu.

## Sơ đồ phần cứng
- **LED 1 (Built-in LED):** Tích hợp sẵn trên bo mạch ESP32 (Chân GPIO 2).
- **LED 2 (External LED):** Cực dương cắm vào chân GPIO 4 (D4), cực âm nối tiếp qua điện trở 1kΩ rồi đi xuống đường GND chung.
- **Nút nhấn:** Một chân kết nối vào chân GPIO 23 (D23), chân cùng phía còn lại nối xuống đường GND chung.

## Cài đặt và Sử dụng
1. Nhân bản (Clone) kho mã nguồn này về máy:
   ```bash
   git clone [https://github.com/ThanhDoan2k5/ESP32-DUALLED.git](https://github.com/ThanhDoan2k5/ESP32-DUALLED.git)
