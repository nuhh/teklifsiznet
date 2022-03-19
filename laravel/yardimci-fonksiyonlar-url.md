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

<a name="urls-method-list"></a>
### URLs

<div class="collection-method-list" markdown="1">

[action](#method-action)
[asset](#method-asset)
[route](#method-route)
[secure_asset](#method-secure-asset)
[secure_url](#method-secure-url)
[to_route](#method-to-route)
[url](#method-url)

</div>

<a name="urls"></a>
## URLs

<a name="method-action"></a>
#### `action()`

The `action` function generates a URL for the given controller action:

    use App\Http\Controllers\HomeController;

    $url = action([HomeController::class, 'index']);

If the method accepts route parameters, you may pass them as the second argument to the method:

    $url = action([UserController::class, 'profile'], ['id' => 1]);

<a name="method-asset"></a>
#### `asset()`

The `asset` function generates a URL for an asset using the current scheme of the request (HTTP or HTTPS):

    $url = asset('img/photo.jpg');

You can configure the asset URL host by setting the `ASSET_URL` variable in your `.env` file. This can be useful if you host your assets on an external service like Amazon S3 or another CDN:

    // ASSET_URL=http://example.com/assets

    $url = asset('img/photo.jpg'); // http://example.com/assets/img/photo.jpg

<a name="method-route"></a>
#### `route()`

The `route` function generates a URL for a given [named route](/docs/{{version}}/routing#named-routes):

    $url = route('route.name');

If the route accepts parameters, you may pass them as the second argument to the function:

    $url = route('route.name', ['id' => 1]);

By default, the `route` function generates an absolute URL. If you wish to generate a relative URL, you may pass `false` as the third argument to the function:

    $url = route('route.name', ['id' => 1], false);

<a name="method-secure-asset"></a>
#### `secure_asset()`

The `secure_asset` function generates a URL for an asset using HTTPS:

    $url = secure_asset('img/photo.jpg');

<a name="method-secure-url"></a>
#### `secure_url()`

The `secure_url` function generates a fully qualified HTTPS URL to the given path. Additional URL segments may be passed in the function's second argument:

    $url = secure_url('user/profile');

    $url = secure_url('user/profile', [1]);

<a name="method-to-route"></a>
#### `to_route()`

The `to_route` function generates a [redirect HTTP response](/docs/{{version}}/responses#redirects) for a given [named route](/docs/{{version}}/routing#named-routes):

    return to_route('users.show', ['user' => 1]);

If necessary, you may pass the HTTP status code that should be assigned to the redirect and any additional response headers as the third and fourth arguments to the `to_route` method:

    return to_route('users.show', ['user' => 1], 302, ['X-Framework' => 'Laravel']);

<a name="method-url"></a>
#### `url()`

The `url` function generates a fully qualified URL to the given path:

    $url = url('user/profile');

    $url = url('user/profile', [1]);

If no path is provided, an `Illuminate\Routing\UrlGenerator` instance is returned:

    $current = url()->current();

    $full = url()->full();

    $previous = url()->previous();
