==========================
Hướng dẫn cài đặt Vinacart
==========================

Cấu hình Server
---------------
**Apache**: Yêu cầu bật modules & extension dưới đây:

- *Module*: mod_rewrite
- *Extension*: ioncube_loader, php_intl, php_curl, php_fileinfo, php_gd2, php_mbstring, php_mysql|php_mysqli|php_pdo_mysql

Cài đặt
-------

1. Chuẩn bị Domain.

Nếu cài đặt trên localhost, sử dụng xampp, wamp.. bạn cần tạo alias (vd: ``vinacart.dev``) thay vì sử dụng tên ``localhost``. Ví dụ:
Edit file `c:/xampp/conf/extra/httpd-vhosts.conf`

::

	<VirtualHost *:80>
	    ServerName vinacart.dev
	    ServerAlias www.vinacart.dev
	    DocumentRoot "C:\xampp\htdocs\vinacart"
	    <Directory "C:\xampp\htdocs\vinacart">
	        Order allow,deny
	        Allow from all
	    </Directory>
		ErrorLog C:\xampp\htdocs\error.txt
	</VirtualHost>

2. Tạo database.

3. Thiết lập quyền truy cập Files.

Nếu chạy web trên hệ điều hành Window + xampp/wamp thì bỏ qua bước này. 
Trường hợp sử dụng Linux, để thiết lập chmod đầy đủ cho các file chúng ta chạy file *caidat.php* trên trình duyệt:
``http://vinacart.dev/caidat.php``

4. Tiến hành cài đặt.

Mở trình duyệt, truy cập trang cài đặt: ``http://vinacart.dev/install/``
Làm theo trình tự các bước (wizard). Điền thông tin đầy đủ rồi nhấn cài đặt, chờ trong vài phút để trình cài đặt hoàn tất.
Xem chi tiết _video hướng dẫn cách cài đặt: http://www.vinacart.net/p/download.html

Chú ý: nếu bạn muốn cài đặt lại vinacart, sử dụng URL sau: ``http://vinacart.dev/install/?rt=install&force=1``
