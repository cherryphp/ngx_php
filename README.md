ngx_php
======
Embedded php script language for nginx-module.

Install
-------
```sh
git clone https://github.com/rryqszq4/ngx_php.git
cd ngx_php

wget 'http://nginx.org/download/nginx-1.6.3.tar.gz'
tar -zxvf nginx-1.6.3.tar.gz
cd nginx-1.6.3

export PHP_BIN=/path/to/php/bin
export PHP_INC=/path/to/php/include/php
export PHP_LIB=/path/to/php/lib

./configure --user=www --group=www \
			--prefix=/path/to/nginx \
			--add-module=/path/to/ngx_php
```

Synopsis
--------
```nginx
server {
	location /php {
		php_content_handler_code "
			echo 'hello ngx_php';
		";
	}
}
```

Test
----
Using the perl of [Test::Nginx](https://github.com/openresty/test-nginx) module to testing, searching and finding out problem in ngx_php. 

```sh
cd /path/to/ngx_php
export PATH=/path/to/ngx_php:$PATH
prove -r t
```

Copyright and License
---------------------
Copyright (c) 2016, rryqszq4 <phpngx@gmail.com>
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
