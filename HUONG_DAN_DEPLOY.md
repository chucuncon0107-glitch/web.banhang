# Hướng Dẫn Deploy Website Lên GitHub Pages

## 🔗 Link Website

Sau khi deploy thành công, website của bạn sẽ có link:

**https://chucuncon0107-glitch.github.io/web_banhang/**

## 📋 Các Bước Deploy

### Cách 1: Deploy Tự Động (Khuyên Dùng)

1. **Bật GitHub Pages trong Repository:**
   - Vào repository: https://github.com/chucuncon0107-glitch/web_banhang
   - Vào Settings → Pages
   - Source: chọn "GitHub Actions"
   - Lưu lại

2. **Push code lên GitHub:**
   ```bash
   git add .
   git commit -m "Setup GitHub Pages deployment"
   git push origin master
   ```

3. **Chờ GitHub Actions tự động deploy:**
   - Vào tab "Actions" trong repository
   - Xem quá trình build và deploy
   - Khi thành công, website sẽ có sẵn tại link trên

### Cách 2: Deploy Thủ Công

1. **Build và deploy:**
   ```bash
   npm run deploy
   ```

2. **Commit và push:**
   ```bash
   git add .
   git commit -m "Deploy to GitHub Pages"
   git push origin master
   ```

## ⚙️ Cấu Hình Đã Thực Hiện

✅ Đã cập nhật `vite.config.js` với base path `/web_banhang/`  
✅ Đã đổi `BrowserRouter` sang `HashRouter` để tương thích với GitHub Pages  
✅ Đã thêm script `deploy` vào `package.json`  
✅ Đã cài đặt `gh-pages` package  
✅ Đã tạo GitHub Actions workflow tự động deploy  

## 🔄 Cập Nhật Website

Mỗi khi bạn thay đổi code:

1. **Nếu dùng GitHub Actions (Cách 1):**
   - Chỉ cần push code lên GitHub
   - GitHub sẽ tự động build và deploy

2. **Nếu dùng deploy thủ công (Cách 2):**
   ```bash
   npm run deploy
   git push origin master
   ```

## 📝 Lưu Ý

- Website sẽ tự động cập nhật sau mỗi lần push code
- Có thể mất 1-2 phút để website hiển thị thay đổi mới
- Đảm bảo branch chính là `master` (hoặc đổi trong `.github/workflows/deploy.yml` nếu là `main`)

## 🆘 Xử Lý Lỗi

Nếu website không hiển thị:
1. Kiểm tra Settings → Pages trong GitHub repository
2. Kiểm tra tab Actions để xem có lỗi build không
3. Đảm bảo base path trong `vite.config.js` đúng với tên repository

