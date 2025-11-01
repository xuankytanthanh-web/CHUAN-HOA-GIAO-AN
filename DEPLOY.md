# Hướng dẫn Deploy lên GitHub và Vercel

## Bước 1: Đẩy code lên GitHub

1. **Khởi tạo Git repository:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Chuẩn hóa giáo án app"
   ```

2. **Tạo repository mới trên GitHub:**
   - Truy cập https://github.com/new
   - Đặt tên repository (ví dụ: `chuan-hoa-giao-an`)
   - Chọn Public hoặc Private
   - **KHÔNG** tích vào "Initialize with README" (vì đã có README.md rồi)
   - Click "Create repository"

3. **Push code lên GitHub:**
   ```bash
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git push -u origin main
   ```

## Bước 2: Deploy lên Vercel

### Cách 1: Deploy qua Vercel Dashboard (Khuyến nghị)

1. **Truy cập Vercel:**
   - Vào https://vercel.com
   - Đăng nhập bằng GitHub account

2. **Tạo Project mới:**
   - Click "Add New..." → "Project"
   - Import repository vừa push lên GitHub
   - Vercel sẽ tự động detect Python và Flask

3. **Cấu hình:**
   - Framework Preset: Không cần chọn (hoặc chọn "Other")
   - Root Directory: `./` (mặc định)
   - Build Command: Không cần (Vercel tự xử lý)
   - Output Directory: Không cần
   - Install Command: `pip install -r requirements.txt` (nếu cần)

4. **Deploy:**
   - Click "Deploy"
   - Chờ vài phút để build
   - Sau khi hoàn tất, bạn sẽ nhận được URL như: `https://your-project.vercel.app`

### Cách 2: Deploy bằng Vercel CLI

1. **Cài đặt Vercel CLI:**
   ```bash
   npm install -g vercel
   ```

2. **Deploy:**
   ```bash
   vercel
   ```

3. **Làm theo hướng dẫn:**
   - Link với project hoặc tạo mới
   - Chọn settings (có thể để mặc định)
   - Sau khi deploy xong, bạn sẽ có URL

## Kiểm tra sau khi deploy

1. Truy cập URL được cung cấp
2. Test upload một file Word
3. Kiểm tra các chức năng:
   - Upload file
   - Preview
   - Adjust
   - Download

## Lưu ý quan trọng

- ✅ Files được lưu trong memory (không persistent) - mỗi request là một function riêng
- ✅ Timeout tối đa: 60 giây (đã cấu hình trong vercel.json)
- ✅ File size limit: 16MB
- ✅ Vercel hỗ trợ Python 3.9

## Troubleshooting

### Lỗi: Module not found
- Kiểm tra `requirements.txt` có đầy đủ dependencies
- Đảm bảo tất cả imports đều có trong requirements.txt

### Lỗi: Timeout
- File quá lớn hoặc xử lý lâu
- Tăng maxDuration trong vercel.json (tối đa 300s cho Pro plan)

### Lỗi: Static files không load
- Kiểm tra cấu hình routes trong vercel.json
- Đảm bảo thư mục `static/` có trong repository

## Cập nhật sau khi deploy

Mỗi khi push code mới lên GitHub:
- Vercel sẽ tự động rebuild và deploy
- Hoặc vào Vercel Dashboard → Deployments → Redeploy
