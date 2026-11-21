# 🚦 KẸT XE BINGO - GDG DevFest Demo

> **Web App vui nhộn biến cơn ác mộng kẹt xe giờ cao điểm thành trò chơi giải trí, kết hợp mạng lưới báo kẹt cộng đồng và bộ gợi ý giờ xuất phát thông minh.**

Dự án là ứng dụng web tĩnh thuần túy (Static SPA), **chỉ gồm `index.html` và `vercel.json`**, không cần build step, không phụ thuộc backend riêng, sẵn sàng deploy ngay lên Vercel hoặc mở trực tiếp trên mọi thiết bị di động / máy tính.

---

## 🌟 Tính Năng Nổi Bật

### 1. 🎯 Bingo Kẹt Xe 5x5
- **Lưới 5x5 quen thuộc**: Ô chính giữa luôn là `FREE: Đang kẹt xe 😩`, 24 ô còn lại được xáo ngẫu nhiên từ kho 48 tình huống đặc sản đường phố Việt Nam (Ninja Lead, xe ôm chở tủ lạnh, đèn đỏ 99s, ngập nước, người mặc áo mưa cánh dơi, tiếng còi xe cứu thương bất lực...).
- **Hiệu ứng trực quan**: Chạm vào ô để đóng dấu "ĐÃ GẶP", hiệu ứng âm thanh tổng hợp từ **Web Audio API** (không cần file âm thanh ngoài, không sợ lỗi tải).
- **Pháo giấy ăn mừng**: Khi đạt đủ 1 hàng ngang, cột dọc hoặc đường chéo, app lập tức nổ pháo giấy confetti và phát nhạc chiến thắng rộn ràng.
- **Đồng hồ kẹt xe**: Đếm thời gian bạn đã kiên nhẫn đứng giữa dòng xe kẹt.
- **Khoe kết quả Wordle-style**: Nút "Khoe kết quả" tự động copy văn bản kèm ma trận emoji (🟩 / ⬜ / ⭐) để chia sẻ lên Facebook, Zalo, Threads.

### 2. 🗺️ Bản Đồ Báo Kẹt Cộng Đồng (TP.HCM)
- **Leaflet + OpenStreetMap**: Bản đồ giao diện tối (Dark Matter), hoàn toàn miễn phí, không cần bất kỳ API key nào.
- **Hỗ trợ Google Maps**: Code tích hợp sẵn hàm tự động chuyển sang Google Maps JavaScript API nếu điền `GOOGLE_MAPS_API_KEY`.
- **Chạm bản đồ để báo điểm kẹt**: Chọn 5 mức độ:
  - 🔴 **Kẹt cứng**
  - 🟡 **Đông đúc**
  - 🌊 **Ngập nước**
  - ⚠️ **Tai nạn**
  - 🚧 **Công trình**
- **Cơ chế tự hết hạn 60 phút**: Marker trên bản đồ tự động mờ dần theo thời gian (100% khi mới báo -> 30% khi sắp hết hạn) và biến mất sau 1 giờ.
- **Chế độ Demo thông minh**: Sẵn sàng 10 điểm nóng giao thông tại TP.HCM (Lăng Cha Cả, Hàng Xanh, Cầu Sài Gòn, Ngã sáu Gò Vấp, Cộng Hòa, Nguyễn Hữu Cảnh...).
- **Nút 👍 "Vẫn còn kẹt"**: Giúp cộng đồng cùng xác nhận độ chính xác của báo cáo.

### 3. ⏰ Gợi Ý Giờ Khởi Hành Thông Minh
- **Biểu đồ cột 24 giờ**: Trực quan hóa mức độ kẹt theo từng khung giờ trong ngày (cao điểm sáng 6h30–8h30, chiều 16h30–19h), tự động tích hợp số lượng báo cáo cộng đồng trực tiếp trong 1 giờ qua.
- **Tính toán giờ đi**: Nhập giờ bạn cần đến nơi và cự ly di chuyển -> App tính toán thời gian di chuyển trong điều kiện kẹt, khuyến nghị giờ xuất phát phù hợp.
- **Gợi ý khung giờ né kẹt**: Đề xuất lùi giờ để tiết kiệm thời gian chờ đèn đỏ và khói bụi.
- **Câu nói vui nhộn**: Tự động hiển thị câu châm ngôn hài hước khớp với từng khung giờ (ví dụ: *"Đi lúc 7h15 thì kịp ăn sáng trên xe luôn, nhích 1 mét cắn 1 miếng bánh mì 🥖"*).

---

## 🚀 Hướng Dẫn Deploy Lên Vercel

### Cách 1: Sử dụng Vercel CLI (Nhanh nhất)
Mở terminal tại thư mục dự án và chạy:
```bash
npx vercel
```
- Khi được hỏi `Set up and deploy?`, gõ `y`.
- Giữ nguyên các thiết lập mặc định (Enter liên tục).
- Để deploy bản production:
```bash
npx vercel --prod
```

### Cách 2: Kéo thả trên giao diện Vercel
1. Truy cập [vercel.com/new](https://vercel.com/new).
2. Kéo thả thư mục chứa `index.html` và `vercel.json` vào khung upload.
3. Bấm **Deploy**. Vercel sẽ cung cấp ngay một tên miền miễn phí dạng `ket-xe-bingo.vercel.app`.

### Cách 3: Deploy thông qua GitHub
1. Commit và push code lên repository:
   ```bash
   git add .
   git commit -m "feat: complete Ket Xe Bingo web app for GDG DevFest"
   git push origin main
   ```
2. Vào [vercel.com/new](https://vercel.com/new), chọn repository `gdg2026` của bạn và bấm **Deploy**.

---

## 🔥 Hướng Dẫn Kết Nối Firebase Realtime (Tùy chọn)

Mặc định ứng dụng chạy ở **Chế độ Demo (localStorage)** để demo ngay lập tức mà không cần tài khoản. Để nhiều điện thoại/máy tính nhìn thấy báo cáo của nhau theo thời gian thực (Realtime):

### Bước 1: Tạo Firebase Project
1. Truy cập [Firebase Console](https://console.firebase.google.com/).
2. Chọn **Add project** và đặt tên dự án (ví dụ `ket-xe-bingo`).
3. Chọn **Build** > **Firestore Database** > **Create database**.

### Bước 2: Thiết lập Security Rules cho Firestore
Vào tab **Rules** trong Firestore Database và dán đoạn cấu hình sau để cho phép cộng đồng đọc/ghi collection `reports`:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /reports/{reportId} {
      allow read, write: if true;
    }
  }
}
```
Bấm **Publish** để lưu.

### Bước 3: Lấy Firebase Config và điền vào `index.html`
1. Vào **Project Settings** (biểu tượng bánh răng) > cuộn xuống mục **Your apps** > chọn biểu tượng Web `</>`.
2. Đăng ký app và copy khối `firebaseConfig`.
3. Mở file [index.html](file:///d:/Dang/Project/Other/DevFest/index.html) và cập nhật biến `FIREBASE_CONFIG` ở dòng ~660:

```javascript
const FIREBASE_CONFIG = {
  apiKey: "AIzaSyD-YourApiKeyHere",
  authDomain: "ket-xe-bingo.firebaseapp.com",
  projectId: "ket-xe-bingo",
  storageBucket: "ket-xe-bingo.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abcdef"
};
```

---

## 🗺️ Hướng Dẫn Dùng Google Maps (Tùy chọn)

Nếu bạn có Google Maps API Key và muốn chuyển từ OpenStreetMap sang Google Maps:
1. Mở file [index.html](file:///d:/Dang/Project/Other/DevFest/index.html).
2. Điền API Key vào biến `GOOGLE_MAPS_API_KEY`:
   ```javascript
   const GOOGLE_MAPS_API_KEY = "AIzaSyYourGoogleMapsApiKey";
   ```
3. Ứng dụng sẽ tự động tải Google Maps JavaScript API và kích hoạt bản đồ Google Maps với giao diện dark theme đồng bộ.

---

## 📱 Trải Nghiệm & Demo Tại GDG DevFest
- Mở trang web trên trình duyệt điện thoại (Chrome/Safari).
- Giao diện được tối ưu chuẩn **Mobile-First**, 3 tab nằm ngay dưới ngón tay cái:
  - 🎯 **Bingo**: Chơi tương tác trực tiếp khi đang kẹt xe.
  - 🗺️ **Bản đồ**: Chạm bất kỳ đâu trên đường để báo kẹt và xem 10 điểm nóng tại TP.HCM.
  - ⏰ **Giờ đi**: Nhấp chọn giờ để nhận mẹo né kẹt và câu nói hài hước.

Chúc bạn có một buổi thuyết trình và demo bùng nổ tại **GDG DevFest 2026**! 🚦🛵🎉
