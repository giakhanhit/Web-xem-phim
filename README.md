# Website xem phim

Dự án website xem phim viết bằng PHP, MySQL/MariaDB, HTML, CSS và JavaScript. Website có trang chủ, danh sách và tìm kiếm phim, trang chi tiết, xem tập phim, đăng ký/đăng nhập và trang quản trị để quản lý phim, tập phim và tài khoản.

## Yêu cầu

- PHP 7.4 trở lên, bật extension `mysqli`. PHP 8.x cũng có thể chạy, nhưng dự án cũ có thể còn một số cảnh báo tương thích.
- MySQL hoặc MariaDB.
- Có thể dùng XAMPP để chạy PHP và MySQL trên Windows.


## Trang quản trị

Trang quản trị nằm tại `/admin/`. Đăng nhập bằng tài khoản trong bảng `user` có `usertype = 99`. Dự án không thiết lập một tài khoản quản trị mới khi cài đặt; hãy kiểm tra dữ liệu database hoặc cập nhật quyền tài khoản của bạn trong phpMyAdmin.

## Lưu ý

- Các file SQL là bản dump cũ; một số phim có thể thiếu ảnh hoặc đường dẫn video không còn hoạt động.
- File `đây là sql.sql` tạo các bảng và dữ liệu nhưng không tự chọn database. Hãy tạo/chọn `assfilm` trong phpMyAdmin trước khi import.
- Chỉ dùng thông tin đăng nhập mẫu trên môi trường phát triển. Đổi mật khẩu và cấu hình database riêng trước khi triển khai lên máy chủ công khai.
