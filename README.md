# Website xem phim

Dự án website xem phim viết bằng PHP, MySQL/MariaDB, HTML, CSS và JavaScript. Website có trang chủ, danh sách và tìm kiếm phim, trang chi tiết, xem tập phim, đăng ký/đăng nhập và trang quản trị để quản lý phim, tập phim và tài khoản.

## Yêu cầu

- PHP 7.4 trở lên, bật extension `mysqli`. PHP 8.x cũng có thể chạy, nhưng dự án cũ có thể còn một số cảnh báo tương thích.
- MySQL hoặc MariaDB.
- Có thể dùng XAMPP để chạy PHP và MySQL trên Windows.

## Cài đặt với XAMPP

1. Chép thư mục dự án vào `C:\xampp\htdocs`.
2. Mở XAMPP Control Panel và khởi động **Apache** cùng **MySQL**.
3. Mở `http://localhost/phpmyadmin`.
4. Tạo database tên `assfilm`, chọn collation `utf8mb4_general_ci` nếu được hỏi.
5. Chọn database `assfilm` vừa tạo, vào **Import**, chọn file `đây là sql.sql` ở thư mục gốc dự án, rồi nhấn **Import**. File này là bản dữ liệu đầy đủ hơn. Không cần import thêm `admin/asset/database/assfilm.sql`; đó là một bản dump cũ hơn và có lệnh tạo database riêng.
6. Kiểm tra cấu hình kết nối trong:
   - `libs/db.php`
   - `admin/libs/db.php`

   Cập nhật `$host`, `$user`, `$pass` và `$db` theo tài khoản MySQL trên máy của bạn. Cấu hình XAMPP mặc định thường dùng host `localhost`, user `root`, mật khẩu để trống và database `assfilm`.
7. Mở website tại `http://localhost/<ten-thu-muc-du-an>/`.

## Chạy bằng PHP tích hợp

Nếu PHP và MySQL đã cài đặt, mở PowerShell tại thư mục dự án và chạy:

```powershell
php -S 127.0.0.1:8000 -t .
```

Sau đó mở `http://127.0.0.1:8000/`. Dừng máy chủ bằng `Ctrl+C`.

Máy chủ tích hợp của PHP chỉ phục vụ trang web; MySQL vẫn cần được khởi động riêng.

## Trang quản trị

Trang quản trị nằm tại `/admin/`. Đăng nhập bằng tài khoản trong bảng `user` có `usertype = 99`. Dự án không thiết lập một tài khoản quản trị mới khi cài đặt; hãy kiểm tra dữ liệu database hoặc cập nhật quyền tài khoản của bạn trong phpMyAdmin.

## Lưu ý

- Các file SQL là bản dump cũ; một số phim có thể thiếu ảnh hoặc đường dẫn video không còn hoạt động.
- File `đây là sql.sql` tạo các bảng và dữ liệu nhưng không tự chọn database. Hãy tạo/chọn `assfilm` trong phpMyAdmin trước khi import.
- Chỉ dùng thông tin đăng nhập mẫu trên môi trường phát triển. Đổi mật khẩu và cấu hình database riêng trước khi triển khai lên máy chủ công khai.
