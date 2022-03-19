# Composer ile Kurulum

Bilgisayarınızda PHP ve Composer yüklü ise, Laravel projenizi direk olarak Composer üzerinden kurabilirsiniz. Uygulama kurulumunuzdan sonra komut pencerenizden `php artisan serve` ile yerel olarak geliştirmeye başlayabilirsiniz.

```shell
composer create-project laravel/laravel kurulum-dizini

cd kurulum-dizini

php artisan serve
```

<a name="the-laravel-installer"></a>
#### Laravel Yükleyici

Tekrardan composer üzerinden global olarak `Laravel Installer` ekleyerek, Laravel kurabilirsiniz.

```shell
composer global require laravel/installer

laravel new kurulum-dizini

cd kurulum-dizini

php artisan serve
```
