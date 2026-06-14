# Sơn Hải — Trình đọc truyện chữ

Trình đọc truyện chữ riêng tư, tối ưu cho điện thoại. Chạy hoàn toàn trong trình duyệt
(không cần server), lưu thư viện và vị trí đọc vào `localStorage` của máy.

## Tính năng

- **Thư viện** với thẻ "Tiếp tục đọc" ghi nhớ chương và vị trí gần nhất.
- **Trình đọc** chữ Việt căn đều, đẹp; chạm giữa màn hình để ẩn/hiện thanh công cụ (chế độ đắm chìm).
- **Tùy chỉnh**: 3 nền (Giấy / Sáng / Tối), 3 phông (Lora / Noto / Sans), cỡ chữ & giãn dòng.
- **Thêm chương**:
  - *Từ link Google Docs* — dán link (mỗi dòng một link), app tự lấy nội dung qua public relay.
  - *Dán văn bản* — phương án dự phòng luôn hoạt động; tự nhận số & tên "Chương …".
- Đã nạp sẵn **Chương 868** để mở là đọc được ngay.

## Chạy

Mở `index.html` (hoặc `Đọc Truyện.html`) bằng trình duyệt. Để dùng như app trên điện thoại,
mở trang rồi chọn **Add to Home Screen**.

Phục vụ qua máy chủ tĩnh bất kỳ, ví dụ:

```bash
python3 -m http.server 8000
# rồi mở http://localhost:8000
```

## Cấu trúc

| File | Vai trò |
|---|---|
| `Đọc Truyện.html` | Giao diện + style (entry chính) |
| `index.html` | Chuyển hướng tới `Đọc Truyện.html` (để chạy ở thư mục gốc / GitHub Pages) |
| `app.js` | Logic: state, đọc, thêm/xóa chương, lưu tiến độ |
| `data/seed.js` | Chương 868 nạp sẵn |

## Lưu ý

- Không có đồng bộ nền tự động — chương mới chỉ xuất hiện khi bạn dán link/văn bản.
- Dữ liệu lưu trên một máy/trình duyệt; xóa site data sẽ mất thư viện & tiến độ đọc.
