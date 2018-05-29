Previous: [301 setup](./301-setup.md)

# 302 Set up the backend 
The backend is a Laravel project. Again, the boilerplate was originally made by Alex on codecourse.

### Requirements:
Same as Laravel requirements:
- Composer
- PHP >= 7.1.3
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension
- Ctype PHP Extension
- JSON PHP Extension

### Get the code
Clone the github repo [nuxt-api-laravel](https://github.com/blomdahldaniel/yrgo-nuxt-api-laravel).

- `git clone https://github.com/blomdahldaniel/yrgo-nuxt-api-laravel`
- `cd yrgo-nuxt-api-laravel`
- copy the `.env.example` to  `.env` and add your database credentials
- `composer install`
- `php artisan key:generate`
- `php artisan jwt:secret`
- `php artisan serve`
- `php artisan migrate --step`
- `php artisan db:seed --class=BooksSeeder`

### G2G
Now you are good to go, we wont spend any time going through the Laravel project but feel free to check it out later!

# Next:
[303 Frontend](./303-frontend.md)
