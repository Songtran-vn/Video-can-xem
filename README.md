# Sổ tay YouTube — bản GitHub/Vercel

Ứng dụng gồm:

- Trang công khai `/`: mọi người xem video.
- Trang riêng `/admin`: thêm, sửa và xóa link YouTube.
- Mật khẩu admin được giữ trong biến môi trường, không ghi vào mã nguồn.
- Dữ liệu dùng PostgreSQL nên đồng bộ trên mọi máy.

## 1. Đưa lên GitHub

Tạo repository trống, giải nén file ZIP này rồi tải toàn bộ các tệp và thư mục lên repository.

## 2. Đưa lên Vercel

1. Vào Vercel → **Add New Project** → chọn repository GitHub.
2. Nhấn **Deploy** với thiết lập mặc định.
3. Trong project Vercel, vào **Storage** → tạo hoặc kết nối cơ sở dữ liệu **Postgres/Neon**. Hệ thống cần biến `DATABASE_URL`.
4. Vào **Settings → Environment Variables**, thêm:
   - `ADMIN_PASSWORD` = mật khẩu admin của sếp (hiện tại là `982605`).
   - `ADMIN_SESSION_SECRET` = một chuỗi bí mật dài, tự đặt, ví dụ từ 32 ký tự trở lên.
5. Vào **Deployments** và Redeploy lần cuối.

Bảng dữ liệu được ứng dụng tự tạo trong lần truy cập đầu tiên.

## Lưu ý bảo mật

Không ghi mật khẩu trực tiếp vào GitHub. Mật khẩu `982605` chỉ gồm sáu chữ số nên nên đổi sang mật khẩu dài hơn sau khi thử nghiệm.
