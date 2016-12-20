==============
Cài đặt chung
==============

Credential
==========

Sử dụng các tài khoản cho các dịch vụ ngoài, như gửi mail..
Các tài khoản này được liệt kê trong file ``system/config/credentials.php``
::

	<?php
	return array(
	    'sendgrid' => array(
	        array(
	            'username'=> 'user1',
	            'password' => 'pass1',
	            'email'=> 'kythuat.hoangweb@gmail.com',
	            'apiKey'=> 'sdfnsdkfr3434fsf',
	        ),
	        array(
	            'username' => 'user2',
	            'password' => 'pass2',
	            'email' => 'laptrinhweb123@gmail.com',
	            'apiKey' => 'sdfsd32y423y432y9erkedfdf'
	        )
	    ),
	    'mailgun' => array(
	        array(

	        )
	    )
	);

.. Chúng tôi bảo trì cập nhật các tài khoản để đảm bảo các website hoạt động tốt, dùng chung các tài khoản đó. 
Để nạp tài khoản bằng cách sửa lại file ``credentials.php``. Sau đó xóa cache của website hoặc truy cập **System > settings > My Settings**.
Chọn **Install & configure** nhấn tab **Refresh Extensions** và nhấn vào Refresh 'Credentials'.
