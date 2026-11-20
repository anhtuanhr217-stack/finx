# 💎 Finix – Quản lý Chi tiêu Cá nhân Thông minh (Personal Finance Web App)

Ứng dụng web quản lý tài chính & chi tiêu cá nhân tối ưu cho người dùng Việt Nam, tích hợp **AI Smart Input** (Google Gemini 2.5 Flash), **Quản lý Ngân sách thông minh**, **Sao lưu dữ liệu Excel UTF-8 BOM** và hỗ trợ **Progressive Web App (PWA)** toàn màn hình.

---

## ✨ Tính năng nổi bật

### 1. 📊 Dashboard Tổng quan (Moneed Style)
- **3 thẻ thống kê thời gian thực:** Tổng số dư khả dụng, Tổng thu tháng này, Tổng chi tháng này (định dạng VNĐ chuẩn).
- **Biểu đồ trực quan (Chart.js):** 
  - *Donut Chart:* Phân bổ chi tiêu chi tiết theo từng danh mục.
  - *Bar Chart:* So sánh dòng tiền Thu/Chi 7 ngày gần nhất.
- **Quản lý đa ví:** Tiền mặt, Tài khoản ngân hàng, Thẻ tín dụng (hỗ trợ số dư âm). Tự động cập nhật số dư khi thêm/sửa/xóa giao dịch.

### 2. 🤖 AI Smart Input (Gemini 2.5 Flash API)
- **Nhập liệu ngôn ngữ tự nhiên:** Tự động bóc tách các câu khẩu ngữ, tiếng lóng tiền tệ Việt Nam (VD: *"Ăn trưa 55k bằng tiền mặt, đổ xăng 100k, lương 15tr vào vcb"*).
- **Quét hóa đơn / Ảnh chuyển khoản:** Tải ảnh lên để Gemini AI tự động trích xuất số tiền, ngày giờ, danh mục và gợi ý ví thanh toán.
- **Xem trước & Xác nhận:** Kiểm tra danh sách giao dịch đã trích xuất trước khi lưu vào hệ thống.
- **Bảo mật:** Lưu Gemini API Key an toàn trong LocalStorage trình duyệt của bạn, không gửi key qua bất kỳ máy chủ trung gian nào.

### 3. 🎯 Quản lý Ngân sách (Budgets)
- Thiết lập hạn mức chi tiêu hàng tháng cho từng danh mục (Ăn uống, Di chuyển, Mua sắm, v.v.).
- **Thanh tiến độ (Progress Bar) thông minh đổi màu 3 nấc:**
  - 🟢 **Xanh lá (< 75%):** Chi tiêu trong tầm kiểm soát.
  - 🟡 **Vàng cam (75% – 99%):** Sắp chạm ngưỡng hạn mức.
  - 🔴 **Đỏ (>= 100%):** Vượt hạn mức chi tiêu kèm nhãn cảnh báo số tiền vượt và banner cảnh báo toàn cục.

### 4. 💾 Sao lưu & Xuất dữ liệu
- **Xuất CSV (Excel) chuẩn UTF-8 BOM:** Chèn mã Byte Order Mark `\uFEFF` chống 100% lỗi font tiếng Việt khi mở trực tiếp bằng Microsoft Excel trên Windows & Mac.
- **Sao lưu & Khôi phục JSON:** Tải file backup toàn bộ dữ liệu (Ví, Danh mục, Lịch sử GD, Ngân sách) và khôi phục khi đổi thiết bị.

### 5. 📱 Progressive Web App (PWA)
- Chạy toàn màn hình như ứng dụng native khi chọn **"Thêm vào Màn hình chính" (Add to Home Screen)** trên Safari iOS hoặc Chrome Android.
- Tích hợp Service Worker cache shell, tải nhanh tức thì và hỗ trợ offline.

---

## 🛠️ Công nghệ sử dụng (Tech Stack)

- **Frontend:** React 18, Tailwind CSS, Lucide Icons, Chart.js 4.4.3
- **AI Engine:** Google Gemini 2.5 Flash API (`@google/genai`)
- **Lưu trữ:** LocalStorage Data Service (thiết kế sẵn lớp trừu tượng để dễ dàng kết nối Supabase / Firebase / REST API)
- **PWA:** Web App Manifest W3C, Service Worker API

---

## 🚀 Hướng dẫn cài đặt & Chạy ứng dụng

### Cách 1: Chạy trực tiếp (Không cần cài đặt Node.js)
Ứng dụng có thể chạy ngay lập tức bằng bất kỳ máy chủ tĩnh (static web server) nào:

```bash
# Sử dụng Python (có sẵn trên hầu hết máy Mac/Linux/Windows)
python3 -m http.server 3838

# Hoặc mở file index.html trực tiếp trên trình duyệt
```
Sau đó truy cập trình duyệt tại `http://localhost:3838`.

### Cách 2: Chạy với Node.js & Vite

```bash
# 1. Cài đặt các thư viện phụ thuộc
npm install

# 2. Khởi chạy dev server
npm run dev

# 3. Đóng gói bản production
npm run build
```

---

## 📄 Bản quyền
Dự án được phân phối dưới giấy phép [MIT License](LICENSE).
