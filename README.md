<p align="center"><img src="logo.png" width="120" alt="Bánh Mì"></p>

<h1 align="center">Bánh Mì Phicomm R1 — bản phát hành</h1>

Trợ lý giọng nói tiếng Việt cho loa **Harman Phicomm R1**: gọi "OK Nabu", hỏi đáp, nghe nhạc,
radio, podcast, báo thức, điều khiển tivi và nhà thông minh, điều khiển từ trình duyệt.

Repo này **chỉ chứa các bản phát hành** (mục [Releases](../../releases)): APK, bộ cài cho
Windows / macOS / Linux / Android (Termux), app điện thoại `BanhMi-DieuKhien.apk`, tệp
`update.json` mà loa đọc để tự cập nhật, và (ở một số bản) firmware màn hình phụ ESP32-S3.
Thay đổi của từng bản: xem ghi chú trong mục [Releases](../../releases).

## Tính năng

- **Trò chuyện bằng giọng nói** — gọi "OK Nabu" (hoặc "Alexa", "Nabi ơi") rồi nói; nói liền một hơi
  "OK Nabu, mấy giờ rồi" cũng được. Máy chủ AI mặc định, Xiaozhi, Vietbot, máy chủ riêng, hoặc gọi
  thẳng **Gemini** / **ChatGPT** bằng API key của bạn (thử nghiệm).
- **Ra lệnh** — "mở bài Nơi này có anh", "mở nhạc Rap Việt", "mở VOV giao thông", "âm lượng 50",
  "đặt báo thức 6 giờ 30 sáng mai", "hẹn giờ 10 phút", "tắt nhạc sau 30 phút", "tắt hết đi".
- **Nghe nhạc** — YouTube, Zing MP3 (ẩn được bài của ca sĩ/kênh không muốn nghe), tìm bài theo
  lời, danh sách yêu thích, 8 kênh radio VOV, podcast; một ô tìm chung cho mọi nguồn.
- **Điều khiển tivi** (Google TV / Android TV) — "bật tivi", "tắt tivi", "bật VTV1" (mở trong
  VTVgo), "mở … trên tivi" (YouTube).
- **Nhà thông minh Tuya / Smart Life** — "bật đèn ngoài", "đặt điều hoà 26 độ": loa gọi thẳng
  Tuya Cloud, không cần Home Assistant. Khoá cửa, gara, két sắt, báo động không bao giờ điều khiển
  từ loa.
- **Bluetooth hai chiều** — phát nhạc từ điện thoại vào loa (chỉnh âm lượng trên điện thoại cả
  dải, tăng bass), hoặc phát ra loa / tai nghe ngoài.
- **Báo thức, hẹn giờ, kịch bản theo giờ** — báo thức chạy cả khi mất mạng; kịch bản cho loa tự nhỏ tiếng, tắt nghe ban đêm.
- **Trang điều khiển ngay trên loa** — `http://<IP-của-loa>:8088` từ điện thoại hoặc máy tính
  cùng Wi-Fi: cài đặt, khung chat, nút micro để nói lệnh từ điện thoại, nhật ký. Đặt được mã PIN.
- **Nút trên đỉnh loa** — bấm 1 lần gọi loa / tắt chuông, 2 lần tắt/bật nghe, 3 lần bật/tắt
  Bluetooth, giữ 6 giây để cài lại Wi-Fi.
- **Nhóm loa, màn hình phụ ESP32-S3, cảnh báo Telegram, tự cập nhật qua mạng.**

## Cài vào loa

Loa và máy cài phải cùng mạng Wi-Fi. Chỉ cần cài một lần; các bản sau loa tự cập nhật.

- **Windows**: tải [BanhMi-R1-Setup.exe](../../releases/latest/download/BanhMi-R1-Setup.exe) rồi
  bấm đúp (bị chặn thì dùng [bản zip](../../releases/latest/download/BanhMi-R1-Windows.zip), giải
  nén, bấm đúp `Cai-dat-BanhMi.bat`).
- **macOS, Linux, Android (Termux)**:

  ```
  curl -fsSL https://github.com/nguyentanduyen885/banhmi-r1-releases/releases/latest/download/install.sh | bash
  ```

Cuối cùng bộ cài in địa chỉ trang điều khiển của loa và mã kích hoạt (nếu loa chưa được kích hoạt).

**Loa mới, chưa vào Wi-Fi nào?** Gõ `M` khi bộ cài hỏi địa chỉ loa, rồi làm theo hướng dẫn (giữ nút
trên đỉnh loa để loa phát mạng "Phicomm R1").

**App điện thoại Android** (thử nghiệm):
[BanhMi-DieuKhien.apk](../../releases/latest/download/BanhMi-DieuKhien.apk) — tự tìm loa trong
nhà, mở trang điều khiển, nói lệnh bằng micro của điện thoại.

## Ghi công

Bánh Mì được phát triển từ [DB-Robot Phicomm R1](https://github.com/ledienbien-ai/db-robot-phincomR1)
(bản 1.5.18) và các dự án nguồn mở mà nó kế thừa (xiaozhi-android, xiaozhi-esp32, Snowboy,
microWakeWord, Opus, OkHttp, NanoHTTPD, TensorFlow Lite…). Máy chủ AI và máy chủ nhạc mặc định là
của DB-Robot.
