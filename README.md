<div align="center">

# 🔄 Google Drive Converter

**Chuyển đổi liên kết Google Drive → link tải trực tiếp**
**và tạo mã QR để quét bằng điện thoại** 📱

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Dependencies](https://img.shields.io/badge/Dependencies-none-brightgreen?style=flat)
![QR API](https://img.shields.io/badge/QR%20API-goqr.me-0e8a16?style=flat)
![Repo Size](https://img.shields.io/github/repo-size/XuanAn2018/google-drive-converter?style=flat)
![Last Commit](https://img.shields.io/github/last-commit/XuanAn2018/google-drive-converter?style=flat)
![Issues](https://img.shields.io/github/issues/XuanAn2018/google-drive-converter?style=flat)

</div>

---

## ✨ Tính năng

- 🔄 **Chuyển đổi liên kết** — biến link chia sẻ Google Drive thành link tải xuống trực tiếp
- 📱 **Tạo mã QR** — sinh mã QR cho link vừa tạo, quét bằng camera điện thoại (iOS / Android) là mở được ngay
- 📋 **Sao chép nhanh** — một nhấp chuột là copy link vào clipboard
- 🔌 **Không cần cài đặt** — chỉ 1 file `HTML`, mở bằng trình duyệt là chạy
- 🔒 **Không lưu dữ liệu** — mọi xử lý diễn ra ngay trên trình duyệt, không có server, không đăng nhập
- 🆓 **Miễn phí 100%** — không giới hạn số lần sử dụng

## 🚀 Cách sử dụng

### Cách 1 — Dùng online

1. Mở trang web của công cụ (GitHub Pages hoặc mở trực tiếp file `index.html`)
2. Dán liên kết Google Drive vào ô nhập liệu
3. Nhấn nút **🔄 Chuyển đổi**
4. Sao chép link tải trực tiếp, **hoặc** nhấn **📱 Tạo mã QR** rồi quét bằng camera điện thoại

### Cách 2 — Chạy trên máy

```bash
git clone https://github.com/XuanAn2018/google-drive-converter.git
cd google-drive-converter
# Mở trực tiếp bằng trình duyệt, hoặc chạy một server tĩnh:
npx serve .
```

## 📥 Hỗ trợ các định dạng liên kết đầu vào

| Định dạng | Ví dụ |
|---|---|
| 🔗 Liên kết chuẩn | `https://drive.google.com/file/d/FILE_ID/view` |
| 🔗 Tham số `id=` | `https://drive.google.com/open?id=FILE_ID` |
| 🆔 File ID thuần | `1ABC123def456GHI789jkl` |

**Đầu ra:**

```
https://drive.google.com/uc?export=download&id=FILE_ID
```

## 📱 Mã QR — hoạt động thế nào?

Mã QR được tạo qua API miễn phí của **[goqr.me](https://goqr.me/api/)** — không cần API key:

```
https://api.qrserver.com/v1/create-qr-code/?size=200x200&data={LINK}
```

| Tham số | Ý nghĩa |
|---|---|
| `size` | Kích thước ảnh QR (ví dụ: `200x200`) |
| `data` | Chuỗi cần mã hóa (link tải trực tiếp, đã `encodeURIComponent`) |

> 💡 **Mẹo:** Nút tạo mã QR hoạt động theo kiểu **gọi đúng 1 lần** — bấm lần đầu mới gọi API, sau đó ẩn/hiện mà không tốn request thừa. Chuyển đổi link mới thì mã QR cũ tự động reset.

## 🛠️ Công nghệ

| Thành phần | Chi tiết |
|---|---|
| 🧱 HTML | Cấu trúc trang, Semantic elements |
| 🎨 CSS | Biến CSS (`:root`), Flexbox, Grid, Responsive |
| ⚙️ JavaScript | Vanilla JS thuần — regex xử lý URL, Clipboard API |
| 🔳 Mã QR | [goqr.me API](https://goqr.me/api/) (`api.qrserver.com`) |

## 📂 Cấu trúc dự án

```
google-drive-converter/
├── index.html    # Toàn bộ giao diện + logic (HTML/CSS/JS)
└── README.md     # Tài liệu này
```

## 🌐 Deploy lên GitHub Pages

1. Vào repo **Settings → Pages**
2. Chọn **Source: Deploy from a branch**
3. Chọn nhánh **main**, thư mục **/ (root)** → **Save**
4. Sau vài phút, trang sẽ có sẵn tại:
   `https://xuanan2018.github.io/google-drive-converter/`

## ⚠️ Lưu ý

- 🔐 Liên kết tải chỉ hoạt động khi tệp được đặt quyền **"Bất kỳ ai có liên kết"**
- 🚫 Google có thể hiện trang **"Xác minh bạn không phải robot"** với tệp lớn — đó là cơ chế chống quét của Google, không phải lỗi của công cụ
- 🌐 Cần có kết nối mạng khi bấm tạo mã QR (API goqr.me)

## 📄 Giấy phép

Miễn phí sử dụng cho mọi mục đích cá nhân và thương mại. ❤️

---

<div align="center">
Made with 🧡 by <a href="https://github.com/XuanAn2018">XuanAn2018</a>
</div>

