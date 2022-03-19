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

The `app_path` function returns the fully qualified path to your application's `app` directory. You may also use the `app_path` function to generate a fully qualified path to a file relative to the application directory:

    $path = app_path();

    $path = app_path('Http/Controllers/Controller.php');

<a name="method-base-path"></a>
#### `base_path()`

The `base_path` function returns the fully qualified path to your application's root directory. You may also use the `base_path` function to generate a fully qualified path to a given file relative to the project root directory:

    $path = base_path();

    $path = base_path('vendor/bin');

<a name="method-config-path"></a>
#### `config_path()`

The `config_path` function returns the fully qualified path to your application's `config` directory. You may also use the `config_path` function to generate a fully qualified path to a given file within the application's configuration directory:

    $path = config_path();

    $path = config_path('app.php');

<a name="method-database-path"></a>
#### `database_path()`

The `database_path` function returns the fully qualified path to your application's `database` directory. You may also use the `database_path` function to generate a fully qualified path to a given file within the database directory:

    $path = database_path();

    $path = database_path('factories/UserFactory.php');

<a name="method-lang-path"></a>
#### `lang_path()`

The `lang_path` function returns the fully qualified path to your application's `lang` directory. You may also use the `lang_path` function to generate a fully qualified path to a given file within the directory:

    $path = lang_path();

    $path = lang_path('en/messages.php');

<a name="method-mix"></a>
#### `mix()`

The `mix` function returns the path to a [versioned Mix file](/docs/{{version}}/mix):

    $path = mix('css/app.css');

<a name="method-public-path"></a>
#### `public_path()`

The `public_path` function returns the fully qualified path to your application's `public` directory. You may also use the `public_path` function to generate a fully qualified path to a given file within the public directory:

    $path = public_path();

    $path = public_path('css/app.css');

<a name="method-resource-path"></a>
#### `resource_path()`

The `resource_path` function returns the fully qualified path to your application's `resources` directory. You may also use the `resource_path` function to generate a fully qualified path to a given file within the resources directory:

    $path = resource_path();

    $path = resource_path('sass/app.scss');

<a name="method-storage-path"></a>
#### `storage_path()`

The `storage_path` function returns the fully qualified path to your application's `storage` directory. You may also use the `storage_path` function to generate a fully qualified path to a given file within the storage directory:

    $path = storage_path();

    $path = storage_path('app/file.txt');
