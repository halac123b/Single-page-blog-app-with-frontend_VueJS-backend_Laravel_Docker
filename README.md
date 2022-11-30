[backend]<br>

`composer create-project --prefer-dist laravel/laravel:^7.0 src` <br>
-> create laravel project (version 7.0)<br><br>

Chuyển đến folder project Laravel: `cd src` | `docker compose run php sh`<br>
`composer require laravel/ui:^2.4` <br>
-> install ui package<br>
`php artisan ui vue --auth` -> authentication<br>
Tạo connection database MySQL<br>
Thay đổi các biến .env: `DB_HOST=mysql` , `DB_PORT` là port của container <br>
Config cache laravel: `php artisan config:cache`<br><br>

Install passort package, chứa các tool advance trong việc login:<br>
`composer require laravel/passport "~9.0"` <br>
Migrate database: `php artisan migrate` <br>
Tạo encrypt key giúp tạo secure access token: `php artisan passport:install` <br>
Thực hiện các setup đc hướng dẫn trong passport document trên Laravel.<br><br>

Chạy API trên Postman<br>
Header: thêm key: Accept - application/json<br>
Với api GET user: thêm key: Authorization -> Bearer {token} <br>

Build container docker: `docker compose up -d`<br>

[frontend] <br>

Create project VueJS: `vue create <name>` <br>
Chạy live server cho VueJS: `npm run serve` <br>
Add library giúp Vue route giữa các page khác nhau: `npm add router`<br>
Install Bootstrap: `npm install bootstrap`<br>
Install axios, library giúp gửi data từ frontend xuống backend: `npm install axios` <br>

[deploy lên server]<br>

- Vào GG Cloud Console<br>
- Tạo 1 VM Instance (cấu hình tự chọn, càng mạng càng $), allow cả HTTP và HTTPS<br>
- Lưu lại external IP của VM<br>
- SSH key: để 2 máy tính kết nối đc với nhau, add public ssh key của máy vào metadata của VM<br>
- cmd: `ssh <username>@<external_ip>` (trong prj vuejs) <br>
- Push project lên 1 repo Github, Server sẽ pull code từ Github và chạy <br>
