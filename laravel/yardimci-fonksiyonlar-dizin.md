# Yardımcı Fonksiyonlar

- [Giriş](#introduction)
- [Fonksiyonlar](#available-methods)

<a name="introduction"></a>
## Giriş

Laravel'in kendi içerisinde kullandığı yardımcı fonksiyonlar bulunmakta, bu fonksiyonları kendi projelerinizde kullanabilirsiniz.

<a name="available-methods"></a>
## Fonksiyonlar

<style>
    .collection-method-list > p {
        column-count: 3; -moz-column-count: 3; -webkit-column-count: 3;
        column-gap: 2em; -moz-column-gap: 2em; -webkit-column-gap: 2em;
    }

    .collection-method-list a {
        display: block;
    }
</style>

<a name="paths-method-list"></a>
### Paths

<div class="collection-method-list" markdown="1">

[app_path](#method-app-path)
[base_path](#method-base-path)
[config_path](#method-config-path)
[database_path](#method-database-path)
[lang_path](#method-lang-path)
[mix](#method-mix)
[public_path](#method-public-path)
[resource_path](#method-resource-path)
[storage_path](#method-storage-path)

</div>

<a name="paths"></a>
## Paths

<a name="method-app-path"></a>
#### `app_path()`

`app_path` fonksiyonu uygulamanızın `app` klasörünü dönderir, ayırca `app_path` fonksiyonu ile `app` klasöründen tam yolu oluşturabilirsiniz.

```php
$path = app_path();

$path = app_path('Http/Controllers/Controller.php');
```

<a name="method-base-path"></a>
#### `base_path()`

`base_path` fonksiyonu uygulamanızın ana dizinini dönderir, ayırca `base_path` fonksiyonu ile ana dizininizden tam yolu oluşturabilirsiniz.

```php
$path = base_path();

$path = base_path('vendor/bin');
```

<a name="method-config-path"></a>
#### `config_path()`

`config_path` fonksiyonu uygulamanızın `config` klasörünü dönderir, ayırca `config_path` fonksiyonu ile `config` klasöründen tam yolu oluşturabilirsiniz.

```php
$path = config_path();

$path = config_path('app.php');
```

<a name="method-database-path"></a>
#### `database_path()`

`database_path` fonksiyonu uygulamanızın `database` klasörünü dönderir, ayırca `database_path` fonksiyonu ile `database` klasöründen tam yolu oluşturabilirsiniz.

```php
$path = database_path();

$path = database_path('factories/UserFactory.php');
```

<a name="method-lang-path"></a>
#### `lang_path()`

`lang_path` fonksiyonu uygulamanızın `lang` klasörünü dönderir, ayırca `lang_path` fonksiyonu ile `lang` klasöründen tam yolu oluşturabilirsiniz.

```php
$path = lang_path();

$path = lang_path('en/messages.php');
```

<a name="method-mix"></a>
#### `mix()`

The `mix` function returns the path to a [versioned Mix file](/docs/{{version}}/mix):

```php
$path = mix('css/app.css');
```

<a name="method-public-path"></a>
#### `public_path()`

`public_path` fonksiyonu uygulamanızın `public` klasörünü dönderir, ayırca `public_path` fonksiyonu ile `public` klasöründen tam yolu oluşturabilirsiniz.

```php
$path = public_path();

$path = public_path('css/app.css');
```

<a name="method-resource-path"></a>
#### `resource_path()`

`resource_path` fonksiyonu uygulamanızın `resources` klasörünü dönderir, ayırca `resource_path` fonksiyonu ile `resources` klasöründen tam yolu oluşturabilirsiniz.

```php
$path = resource_path();

$path = resource_path('sass/app.scss');
```

<a name="method-storage-path"></a>
#### `storage_path()`

`storage_path` fonksiyonu uygulamanızın `storage` klasörünü dönderir, ayırca `storage_path` fonksiyonu ile `storage` klasöründen tam yolu oluşturabilirsiniz.

```php
$path = storage_path();

$path = storage_path('app/file.txt');
```
