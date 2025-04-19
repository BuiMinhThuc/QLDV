# Hướng dẫn Deploy lên Railway

## Yêu cầu
- Tài khoản Railway
- Git repository của dự án

## Các bước deploy

1. Đăng nhập vào Railway và tạo một project mới
2. Kết nối với Git repository của bạn
3. Railway sẽ tự động detect và build dự án dựa trên `railway.toml` và `Dockerfile`
4. Cấu hình các biến môi trường trong Railway:
   - `ConnectionStrings__DefaultConnection`: Connection string của database
   - `AppSettings__SecretKey`: Secret key cho JWT

## Cấu hình môi trường

### Development
- Sử dụng file `appsettings.Development.json`
- Chạy local với `dotnet run`

### Production
- Sử dụng các biến môi trường trong Railway
- Railway sẽ tự động build và deploy khi có thay đổi từ Git

## Lưu ý
- Đảm bảo connection string trong Railway phù hợp với môi trường production
- Kiểm tra logs trong Railway dashboard nếu có lỗi
- Có thể cần chạy migrations database sau khi deploy 