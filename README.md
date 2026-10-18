<p align="center"><img src="logo.png" width="120" alt="Bánh Mì"></p>

<h1 align="center">Bánh Mì Phicomm R1 — bản phát hành</h1>

Trợ lý giọng nói tiếng Việt cho loa **Harman Phicomm R1**: gọi "OK Nabu", hỏi đáp, nghe nhạc,
radio, podcast, báo thức, nhóm loa, điều khiển từ trình duyệt.

Repo này **chỉ chứa các bản phát hành** (mục [Releases](../../releases)): APK, bộ cài cho
Windows / macOS / Linux / Android (Termux), tệp `update.json` mà loa đọc để tự cập nhật, và firmware
màn hình phụ ESP32-S3.

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

## Ghi công

Bánh Mì được phát triển từ [DB-Robot Phicomm R1](https://github.com/ledienbien-ai/db-robot-phincomR1)
(bản 1.5.18) và các dự án nguồn mở mà nó kế thừa (xiaozhi-android, xiaozhi-esp32, Snowboy,
microWakeWord, Opus, OkHttp, NanoHTTPD, TensorFlow Lite…). Máy chủ AI và máy chủ nhạc mặc định là
của DB-Robot.
