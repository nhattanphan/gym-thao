# Gym Thảo — web app

Bản web riêng của "Tập gym cùng Thảo": chạy toàn màn hình trên iPhone, có icon riêng,
không cần tài khoản Claude, mở được cả khi mất mạng.

## Các file
- `index.html` — toàn bộ app
- `manifest.webmanifest` — tên, icon, màu khi cài lên màn hình chính
- `sw.js` — cho app mở được khi không có mạng
- `icons/` — icon 180/192/512 px

## Đưa lên mạng (chọn 1 cách)

### A. GitHub Pages (miễn phí, không cần cài gì)
1. Vào github.com → New repository → tên ví dụ `gym-thao` → Public → Create.
2. Bấm "uploading an existing file", kéo cả 4 mục (index.html, manifest.webmanifest, sw.js, thư mục icons) vào → Commit.
3. Settings → Pages → Source: "Deploy from a branch", Branch: `main`, thư mục `/ (root)` → Save.
4. Sau 1–2 phút có link dạng `https://<tên-github>.github.io/gym-thao/`.

### B. Firebase Hosting (nếu muốn dùng tên miền của bạn)
`firebase init hosting` (public directory = thư mục này) rồi `firebase deploy`.

## Cài lên iPhone của Thảo
Mở link bằng Safari → nút Chia sẻ → "Thêm vào MH chính" → Thêm.

## Lưu ý về dữ liệu
- Dữ liệu lưu trên chính điện thoại (localStorage), không gửi đi đâu.
- iOS có thể xoá dữ liệu của web app nếu lâu không mở. Trong tab Hướng dẫn có nút
  "Tải file sao lưu" và "Khôi phục từ file": nên sao lưu mỗi tháng.

## Cập nhật app
Sửa `index.html`, đổi `VERSION` trong `sw.js` (ví dụ `gym-thao-v2`), upload lại.
Lần mở sau app tự lấy bản mới; dữ liệu vẫn giữ nguyên.
