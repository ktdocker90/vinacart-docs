===========================
Công cụ build theme tự động
===========================

Đây là phần mềm tạo tpl tự động từ HTML đã được tách bóc gọn từ một bản HTML của giao diện gốc.

Khái niệm/Thuật ngữ
===================
Các blocks & pages được thiết kế vào các file HTML riêng biệt, chúng có cấu trúc khác nhau tùy vào giao diện gốc. Trong đó một số block/page có sử dụng chung cấu trúc HTML như tabs, ul list,..sẽ được kế thừa và tự động tạo không cần thiết kế lại HTML cho chúng.

- block/page gọi chung là block.
- module: là những thành phần HTML dùng chung cho block.

Build Form
==========

- Theme: chọn không gian làm việc với theme nào?
- web data: xác định dữ liệu mẫu của theme.

Bạn có thể build từng block/page/.. hoặc build toàn bộ theme với nút **Build**. Để build từng thành phần một, nhấn vào lựa chọn "Build Option",một hộp thoại hiện ra cho phép bạn chọn những block/page muốn build, ví dụ trường hợp bạn đã sửa lại một số thứ và chỉ muốn build chúng.

Nhấn Build để bắt đầu.


theme.xml
=========
Đây là File cấu hình cho theme. File này có khai báo asset (.css, .js), giao diện block & các cấu hình khác như ảnh, cũng sẽ được cập nhật tự động bằng cách nhấn vào nút ``Update theme.xml``

Một khi file này được tạo, những module có sử dụng cho việc tạo ``theme.xml`` sẽ được đánh đấu là đã build trong menu Themes List có nói ở bên dưới.

Global/Menu
===========

CSS class/id List
^^^^^^^^^^^^^^^^^
Nội dung Shortcode được điền vào HTML để thay thế class khi build ra file .tpl. Trang này liệt kê danh sách những class có thể sử dụng. Bạn điền đầy đủ vào các trường tùy theo thiết kế giao diện HTML.

Đoạn shortcode hiện ra ở bên dưới, bạn copy vào nội dung html. VD:
..
	<form class="class1 [class:form_wrapper] class2"></form>

Common HTML Template
^^^^^^^^^^^^^^^^^^^^
Các thành phần HTML dùng chung trong block/page, như nút , message, tabs, form input..
Nhập đoạn HTML vào trình soạn thảo, và nhấn nút Lưu.


Blocks use module
^^^^^^^^^^^^^^^^^
Phần này thiết lập giao diện module cho block, cho những block có sử dụng module (tức là block đó không có giao diện HTML riêng mà dùng chung thành phần HTML, gọi là module). 

Một module có thể tạo nhiều file html khai báo giao diện khác nhau cho module đó, có file chính trùng với tên module & các file khác có hậu tố ``-n``. 
VD:
module tabs có các giao diện: tabs.html (giao diện chính), tabs-1.html, tabs-2.html,..

Ứng dụng: Nếu 2 block dùng chung module, nhưng chúng có giao diện HTML khác nhau. Tại trang này chọn giao diện HTML mong muốn cho module sử dụng cho từng block.

Lưu ý: mỗi block kế thừa 1 module.


Themes List
^^^^^^^^^^^
Thống kê dữ liệu các themes được tạo trong hệ thống. Mỗi theme có liệt kê trạng thái của các block (biểu tượng mầu xanh: block có sửa lại nhưng chưa build, mầu xám: block đã build).

Nhấn Delete để xóa dữ liệu của theme ra khỏi CSDL.
Nhấn Reset để đánh dấu tất cả các block cần build lại.


Template
========
Panel này liệt kê những file .tpl đã được build tự động. Nhấn vào file hoặc chuột phải chọn ``edit`` để sửa nội dung. Để xóa file chuột phải chọn ``Delete``.


Inspect HTML
============
Phần này liệt kê những file html được tạo. Để thêm file có 2 cách :

- Sử dụng công cụ inspect để khoanh vùng block và các thành phần chi tiết của block. Sau khi đã đánh dấu đầy đủ, chuột phải tại vùng block có mầu đỏ chọn edit & nhấn Export Block. File HTML của block đó sẽ được lưu lại vào thư mục ``html_saved/<theme>``. 
Tại đó Bạn cũng xem trước nội dung tpl đã sinh ra để kiểm tra bạn đã đánh dấu đúng thành phần của block hay không.

- Soạn trực tiếp nội dung HTML của block: cách này nhanh gọn & chính xác hơn. Để thêm file nhấn nút ``+`` bên cạnh panel, hộp thoại xuất hiện chọn file và nhấn nút Ok.
Bạn sẽ thây nội dung mẫu của block trong cửa sổ soạn thảo. Những thành phần của block được highlight mẫu xanh, cho biết vị trí của chúng đặt trong thuộc tính class trong nội dung HTML.

Tên class có tiền tố ``__vnc-`` sau đó là tên thành phần. Trong đó có tên class chính bao toàn bộ nội dung block, có dạng: ``__vnc-block-<block_name>``
Chú ý: không được thiếu class này.

Để chèn class đánh dấu, chọn combobox trên thanh toolbar. Build block ra file .tpl nhấn nút play bên cạnh. FIle .tpl được lưu tại thư mục ``template/<theme>``


HTML Pages
==========
Panel này liệt kê những file HTML của giao diện gốc, nhấn vào để xem và sử dụng công cụ inspect. Tính năng inspect sẽ trích xuất file HTML cho từng block.


Export
======
Tùy chọn Export zip với các file html đã trích xuất, các file .tpl đã build & toàn bộ nội dung theme.


Upload HTML
===========
Tại trang này cho phép bạn tải lên file zip chứa file .html của giao diện HTML gốc hoặc các file html được trích xuất nếu bạn có.
