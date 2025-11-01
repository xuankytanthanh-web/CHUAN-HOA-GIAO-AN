# Trang web Chuẩn hóa Giáo án - Thầy Xuân Kỷ

Ứng dụng web để chuẩn hóa giáo án theo Nghị định 30/2020/NĐ-CP của Chính phủ Việt Nam.

## Chức năng

1. **Upload giáo án**: Upload file Word (.docx, .doc) lên hệ thống
2. **Chuẩn hóa tự động**: 
   - Áp dụng thể thức hành chính theo Nghị định 30/2020/NĐ-CP
   - Bỏ các bullets thừa ở đầu dòng
   - Chuẩn hóa font chữ (Times New Roman), cỡ chữ, khoảng cách
   - Chuẩn hóa lề trang theo quy định
3. **Xem thử**: Hiển thị nội dung đã chuẩn hóa để kiểm tra
4. **Điều chỉnh**: Cho phép giáo viên điều chỉnh thêm:
   - Cỡ chữ
   - Khoảng cách dòng
   - Lề trang
5. **Tải về**: Xuất file đã chuẩn hóa về máy tính

## 🚀 Deploy lên Vercel (Khuyến nghị)

Dự án đã được cấu hình sẵn để deploy lên Vercel một cách dễ dàng!

### Cách deploy lên Vercel:

1. **Đẩy code lên GitHub:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git push -u origin main
   ```

2. **Deploy trên Vercel:**
   - Truy cập [vercel.com](https://vercel.com)
   - Đăng nhập và chọn "New Project"
   - Import repository từ GitHub
   - Vercel sẽ tự động phát hiện cấu hình và deploy
   - Chờ vài phút để build hoàn tất
   - Truy cập URL được cung cấp!

### Hoặc deploy bằng Vercel CLI:

```bash
npm i -g vercel
vercel
```

## 💻 Chạy local development

### Yêu cầu hệ thống

- Python 3.7 trở lên
- pip (Python package manager)

### Cài đặt

1. Cài đặt các thư viện cần thiết:
```bash
pip install -r requirements.txt
```

### Chạy ứng dụng

1. Khởi động server:
```bash
python app.py
```

2. Mở trình duyệt và truy cập:
```
http://localhost:5000
```

## Cách sử dụng

1. **Upload file**: Chọn hoặc kéo thả file Word vào khu vực upload
2. **Xem preview**: Kiểm tra nội dung đã được chuẩn hóa
3. **Điều chỉnh** (tùy chọn): Thay đổi cỡ chữ, khoảng cách, lề trang nếu cần
4. **Tải về**: Tải file đã chuẩn hóa về máy tính

## Quy định chuẩn hóa (Nghị định 30/2020/NĐ-CP)

- **Font chữ**: Times New Roman
- **Cỡ chữ**: 13-14pt (nội dung), 14-16pt (tiêu đề)
- **Khoảng cách dòng**: 1.2-1.3 lines
- **Lề trang**: 
  - Trên: 2cm
  - Dưới: 2cm
  - Trái: 3cm
  - Phải: 2cm
- **Căn lề**: Căn đều (justify) cho nội dung, căn giữa cho tiêu đề
- **Bỏ bullets thừa**: Tự động xóa các ký tự bullets và số thứ tự không cần thiết

## Cấu trúc thư mục

```
CHUAN HOA GIAO AN/
├── api/
│   └── index.py       # Flask app cho Vercel
├── app.py              # Flask app cho local development
├── requirements.txt    # Dependencies
├── vercel.json        # Cấu hình Vercel
├── README.md          # Tài liệu
├── templates/
│   └── index.html     # Frontend HTML
└── static/
    ├── style.css      # CSS styling
    └── script.js      # JavaScript logic
```

## Lưu ý

- File upload tối đa: 16MB
- Chỉ hỗ trợ định dạng .docx và .doc
- Vercel sử dụng serverless functions với timeout 60 giây
- Files được lưu trong memory trên Vercel (không persistent storage)

## Tác giả

Thầy Xuân Kỷ

## Giấy phép

Sử dụng cho mục đích giáo dục
