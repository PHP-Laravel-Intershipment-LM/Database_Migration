# Database With Migration In Laravel

1.  **Migration là gì?**

Migration giống như một hệ thống quản lý phiên bản giống như Git nhưng
dành cho cơ sở dữ liệu của bạn. Migration cho phép bạn định nghĩa các
bảng trong CSDL, định nghĩa nội dung các bảng cũng như cập nhật thay đổi
các bảng đó hoàn toàn bằng PHP. Đồng thời các thao tác với CSDL này còn
có thể sử dụng trên các loại CSDL khác nhau như MySQL, SQL Server,
Postgres, \... mà không cần phải chỉnh sửa lại code theo CSDL sử dụng.

Điều kiện tiên quyết để chạy migration một cách thành công:

-   Phải có kết nối với database .

-   Migrations muốn sử dụng được thì phải nằm trong thư mục
    database\\migrations

2.  **Tạo CSDL bằng Migration**

Tạo một migration trong Laravel bằng lệnh:

> php artisan make:migration create\_table\_names\_table \--create=names

Trong thư mục _database/migrations_ xuất hiện một file có tên
> \...\_create\_table\_names\_table.php

Mở file đó lên, chú ý phương thức _up()_, đó là phương thức sẽ giúp chúng
ta tạo bảng. Chúng ta chèn thêm các cột hay chỉnh sửa các cột không muốn
ở trong đây.

Sau khi hoàn thành chỉnh sửa, tiến hành chạy lệnh sau để tạo bảng tương
ứng trong csdl: 
> php artisan migrate

-   Chú ý: 
  - Nếu như csdl dữ liệu đã có tồn tại các bảng và chúng ta muốn
    rollback toàn bộ các migrate trước, chúng ta thêm tùy chọn
    refresh lúc tạo như sau: 
  > php artisan migrate:refresh
  
  - Nếu như muốn xóa toàn bộ bảng trước khi chạy, thêm tùy chọn fresh như sau:
  > php artisan migrate:fresh