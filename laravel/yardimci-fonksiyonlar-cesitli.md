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

<a name="miscellaneous-method-list"></a>
### Miscellaneous

<div class="collection-method-list" markdown="1">

[abort](#method-abort)
[abort_if](#method-abort-if)
[abort_unless](#method-abort-unless)
[app](#method-app)
[auth](#method-auth)
[back](#method-back)
[bcrypt](#method-bcrypt)
[blank](#method-blank)
[broadcast](#method-broadcast)
[cache](#method-cache)
[class_uses_recursive](#method-class-uses-recursive)
[collect](#method-collect)
[config](#method-config)
[cookie](#method-cookie)
[csrf_field](#method-csrf-field)
[csrf_token](#method-csrf-token)
[decrypt](#method-decrypt)
[dd](#method-dd)
[dispatch](#method-dispatch)
[dump](#method-dump)
[encrypt](#method-encrypt)
[env](#method-env)
[event](#method-event)
[filled](#method-filled)
[info](#method-info)
[logger](#method-logger)
[method_field](#method-method-field)
[now](#method-now)
[old](#method-old)
[optional](#method-optional)
[policy](#method-policy)
[redirect](#method-redirect)
[report](#method-report)
[request](#method-request)
[rescue](#method-rescue)
[resolve](#method-resolve)
[response](#method-response)
[retry](#method-retry)
[session](#method-session)
[tap](#method-tap)
[throw_if](#method-throw-if)
[throw_unless](#method-throw-unless)
[today](#method-today)
[trait_uses_recursive](#method-trait-uses-recursive)
[transform](#method-transform)
[validator](#method-validator)
[value](#method-value)
[view](#method-view)
[with](#method-with)

</div>

<a name="miscellaneous"></a>
## Miscellaneous

<a name="method-abort"></a>
#### `abort()`

The `abort` function throws [an HTTP exception](/docs/{{version}}/errors#http-exceptions) which will be rendered by the [exception handler](/docs/{{version}}/errors#the-exception-handler):

    abort(403);

You may also provide the exception's message and custom HTTP response headers that should be sent to the browser:

    abort(403, 'Unauthorized.', $headers);

<a name="method-abort-if"></a>
#### `abort_if()`

The `abort_if` function throws an HTTP exception if a given boolean expression evaluates to `true`:

    abort_if(! Auth::user()->isAdmin(), 403);

Like the `abort` method, you may also provide the exception's response text as the third argument and an array of custom response headers as the fourth argument to the function.

<a name="method-abort-unless"></a>
#### `abort_unless()`

The `abort_unless` function throws an HTTP exception if a given boolean expression evaluates to `false`:

    abort_unless(Auth::user()->isAdmin(), 403);

Like the `abort` method, you may also provide the exception's response text as the third argument and an array of custom response headers as the fourth argument to the function.

<a name="method-app"></a>
#### `app()`

The `app` function returns the [service container](/docs/{{version}}/container) instance:

    $container = app();

You may pass a class or interface name to resolve it from the container:

    $api = app('HelpSpot\API');

<a name="method-auth"></a>
#### `auth()`

The `auth` function returns an [authenticator](/docs/{{version}}/authentication) instance. You may use it as an alternative to the `Auth` facade:

    $user = auth()->user();

If needed, you may specify which guard instance you would like to access:

    $user = auth('admin')->user();

<a name="method-back"></a>
#### `back()`

The `back` function generates a [redirect HTTP response](/docs/{{version}}/responses#redirects) to the user's previous location:

    return back($status = 302, $headers = [], $fallback = '/');

    return back();

<a name="method-bcrypt"></a>
#### `bcrypt()`

The `bcrypt` function [hashes](/docs/{{version}}/hashing) the given value using Bcrypt. You may use this function as an alternative to the `Hash` facade:

    $password = bcrypt('my-secret-password');

<a name="method-blank"></a>
#### `blank()`

Verilen değerin "boş" olduğunu belirler.

```php
blank('');
blank('   ');
blank(null);
blank(collect());
// doğru

blank(0);
blank(true);
blank(false);
// yanlış
```

`blank` fonksiyonunun tersi için [`filled`](#method-filled) fonksiyonunu inceleyebilirsiniz.

<a name="method-broadcast"></a>
#### `broadcast()`

The `broadcast` function [broadcasts](/docs/{{version}}/broadcasting) the given [event](/docs/{{version}}/events) to its listeners:

    broadcast(new UserRegistered($user));

    broadcast(new UserRegistered($user))->toOthers();

<a name="method-cache"></a>
#### `cache()`

The `cache` function may be used to get values from the [cache](/docs/{{version}}/cache). If the given key does not exist in the cache, an optional default value will be returned:

    $value = cache('key');

    $value = cache('key', 'default');

You may add items to the cache by passing an array of key / value pairs to the function. You should also pass the number of seconds or duration the cached value should be considered valid:

    cache(['key' => 'value'], 300);

    cache(['key' => 'value'], now()->addSeconds(10));

<a name="method-class-uses-recursive"></a>
#### `class_uses_recursive()`

The `class_uses_recursive` function returns all traits used by a class, including traits used by all of its parent classes:

    $traits = class_uses_recursive(App\Models\User::class);

<a name="method-collect"></a>
#### `collect()`

The `collect` function creates a [collection](/docs/{{version}}/collections) instance from the given value:

    $collection = collect(['taylor', 'abigail']);

<a name="method-config"></a>
#### `config()`

The `config` function gets the value of a [configuration](/docs/{{version}}/configuration) variable. The configuration values may be accessed using "dot" syntax, which includes the name of the file and the option you wish to access. A default value may be specified and is returned if the configuration option does not exist:

    $value = config('app.timezone');

    $value = config('app.timezone', $default);

You may set configuration variables at runtime by passing an array of key / value pairs. However, note that this function only affects the configuration value for the current request and does not update your actual configuration values:

    config(['app.debug' => true]);

<a name="method-cookie"></a>
#### `cookie()`

The `cookie` function creates a new [cookie](/docs/{{version}}/requests#cookies) instance:

```php
$cookie = cookie('name', 'value', $minutes);
```

<a name="method-csrf-field"></a>
#### `csrf_field()`

The `csrf_field` function generates an HTML `hidden` input field containing the value of the CSRF token. For example, using [Blade syntax](/docs/{{version}}/blade):

```php
{{ csrf_field() }}
```

<a name="method-csrf-token"></a>
#### `csrf_token()`

The `csrf_token` function retrieves the value of the current CSRF token:

```php
$token = csrf_token();
```

<a name="method-decrypt"></a>
#### `decrypt()`

The `decrypt` function [decrypts](/docs/{{version}}/encryption) the given value. You may use this function as an alternative to the `Crypt` facade:

```php
$password = decrypt($value);
```

<a name="method-dd"></a>
#### `dd()`

The `dd` function dumps the given variables and ends execution of the script:

```php
dd($value);

dd($value1, $value2, $value3, ...);
```

If you do not want to halt the execution of your script, use the [`dump`](#method-dump) function instead.

<a name="method-dispatch"></a>
#### `dispatch()`

The `dispatch` function pushes the given [job](/docs/{{version}}/queues#creating-jobs) onto the Laravel [job queue](/docs/{{version}}/queues):

```php
dispatch(new App\Jobs\SendEmails);
```

<a name="method-dump"></a>
#### `dump()`

The `dump` function dumps the given variables:

```php
dump($value);

dump($value1, $value2, $value3, ...);
```

If you want to stop executing the script after dumping the variables, use the [`dd`](#method-dd) function instead.

<a name="method-encrypt"></a>
#### `encrypt()`

The `encrypt` function [encrypts](/docs/{{version}}/encryption) the given value. You may use this function as an alternative to the `Crypt` facade:

```php
$secret = encrypt('my-secret-value');
```

<a name="method-env"></a>
#### `env()`

The `env` function retrieves the value of an [environment variable](/docs/{{version}}/configuration#environment-configuration) or returns a default value:

```php
$env = env('APP_ENV');

$env = env('APP_ENV', 'production');
```

> {note} If you execute the `config:cache` command during your deployment process, you should be sure that you are only calling the `env` function from within your configuration files. Once the configuration has been cached, the `.env` file will not be loaded and all calls to the `env` function will return `null`.

<a name="method-event"></a>
#### `event()`

The `event` function dispatches the given [event](/docs/{{version}}/events) to its listeners:

```php
event(new UserRegistered($user));
```

<a name="method-filled"></a>
#### `filled()`

Verilen değerin "boş" olmadığını belirler.

```php
filled(0);
filled(true);
filled(false);
// doğru

filled('');
filled('   ');
filled(null);
filled(collect());
// yanlış
```

`filled` fonksiyonunun tersi için [`blank`](#method-blank) fonksiyonunu inceleyebilirsiniz.

<a name="method-info"></a>
#### `info()`

The `info` function will write information to your application's [log](/docs/{{version}}/logging):

```php
info('Some helpful information!');
```

An array of contextual data may also be passed to the function:

```php
info('User login attempt failed.', ['id' => $user->id]);
```

<a name="method-logger"></a>
#### `logger()`

The `logger` function can be used to write a `debug` level message to the [log](/docs/{{version}}/logging):

```php
logger('Debug message');
```

An array of contextual data may also be passed to the function:

```php
logger('User has logged in.', ['id' => $user->id]);
```

A [logger](/docs/{{version}}/errors#logging) instance will be returned if no value is passed to the function:

```php
logger()->error('You are not allowed here.');
```

<a name="method-method-field"></a>
#### `method_field()`

The `method_field` function generates an HTML `hidden` input field containing the spoofed value of the form's HTTP verb. For example, using [Blade syntax](/docs/{{version}}/blade):

```php
<form method="POST">
    {{ method_field('DELETE') }}
</form>
```

<a name="method-now"></a>
#### `now()`

The `now` function creates a new `Illuminate\Support\Carbon` instance for the current time:

```php
$now = now();
```

<a name="method-old"></a>
#### `old()`

The `old` function [retrieves](/docs/{{version}}/requests#retrieving-input) an [old input](/docs/{{version}}/requests#old-input) value flashed into the session:

```php
$value = old('value');

$value = old('value', 'default');
```

<a name="method-optional"></a>
#### `optional()`

The `optional` function accepts any argument and allows you to access properties or call methods on that object. If the given object is `null`, properties and methods will return `null` instead of causing an error:

```php
return optional($user->address)->street;

{!! old('name', optional($user)->name) !!}
```

The `optional` function also accepts a closure as its second argument. The closure will be invoked if the value provided as the first argument is not null:

```php
return optional(User::find($id), function ($user) {
    return $user->name;
});
```

<a name="method-policy"></a>
#### `policy()`

The `policy` method retrieves a [policy](/docs/{{version}}/authorization#creating-policies) instance for a given class:

```php
$policy = policy(App\Models\User::class);
```

<a name="method-redirect"></a>
#### `redirect()`

The `redirect` function returns a [redirect HTTP response](/docs/{{version}}/responses#redirects), or returns the redirector instance if called with no arguments:

```php
return redirect($to = null, $status = 302, $headers = [], $https = null);

return redirect('/home');

return redirect()->route('route.name');
```

<a name="method-report"></a>
#### `report()`

The `report` function will report an exception using your [exception handler](/docs/{{version}}/errors#the-exception-handler):

```php
report($e);
```

The `report` function also accepts a string as an argument. When a string is given to the function, the function will create an exception with the given string as its message:

```php
report('Something went wrong.');
```

<a name="method-request"></a>
#### `request()`

The `request` function returns the current [request](/docs/{{version}}/requests) instance or obtains an input field's value from the current request:

```php
$request = request();

$value = request('key', $default);
```

<a name="method-rescue"></a>
#### `rescue()`

The `rescue` function executes the given closure and catches any exceptions that occur during its execution. All exceptions that are caught will be sent to your [exception handler](/docs/{{version}}/errors#the-exception-handler); however, the request will continue processing:

```php
return rescue(function () {
    return $this->method();
});
```

You may also pass a second argument to the `rescue` function. This argument will be the "default" value that should be returned if an exception occurs while executing the closure:

```php
return rescue(function () {
    return $this->method();
}, false);

return rescue(function () {
    return $this->method();
}, function () {
    return $this->failure();
});
```

<a name="method-resolve"></a>
#### `resolve()`

The `resolve` function resolves a given class or interface name to an instance using the [service container](/docs/{{version}}/container):

```php
$api = resolve('HelpSpot\API');
```

<a name="method-response"></a>
#### `response()`

The `response` function creates a [response](/docs/{{version}}/responses) instance or obtains an instance of the response factory:

```php
return response('Hello World', 200, $headers);

return response()->json(['foo' => 'bar'], 200, $headers);
```

<a name="method-retry"></a>
#### `retry()`

The `retry` function attempts to execute the given callback until the given maximum attempt threshold is met. If the callback does not throw an exception, its return value will be returned. If the callback throws an exception, it will automatically be retried. If the maximum attempt count is exceeded, the exception will be thrown:

```php
return retry(5, function () {
    // Attempt 5 times while resting 100ms between attempts...
}, 100);
```

If you would like to manually calculate the number of milliseconds to sleep between attempts, you may pass a closure as the third argument to the `retry` function:

```php
return retry(5, function () {
    // ...
}, function ($attempt) {
    return $attempt * 100;
});
```

For convenience, you may provide an array as the first argument to the `retry` function. This array will be used to determine how many milliseconds to sleep between subsequent attempts:

```php
return retry([100, 200] function () {
    // Sleep for 100ms on first retry, 200ms on second retry...
});
```

To only retry under specific conditions, you may pass a closure as the fourth argument to the `retry` function:

```php
return retry(5, function () {
    // ...
}, 100, function ($exception) {
    return $exception instanceof RetryException;
});
```

<a name="method-session"></a>
#### `session()`

The `session` function may be used to get or set [session](/docs/{{version}}/session) values:

```php
$value = session('key');
```

You may set values by passing an array of key / value pairs to the function:

```php
session(['chairs' => 7, 'instruments' => 3]);
```

The session store will be returned if no value is passed to the function:

```php
$value = session()->get('key');

session()->put('key', $value);
```

<a name="method-tap"></a>
#### `tap()`

The `tap` function accepts two arguments: an arbitrary `$value` and a closure. The `$value` will be passed to the closure and then be returned by the `tap` function. The return value of the closure is irrelevant:

```php
$user = tap(User::first(), function ($user) {
    $user->name = 'taylor';

    $user->save();
});
```

If no closure is passed to the `tap` function, you may call any method on the given `$value`. The return value of the method you call will always be `$value`, regardless of what the method actually returns in its definition. For example, the Eloquent `update` method typically returns an integer. However, we can force the method to return the model itself by chaining the `update` method call through the `tap` function:

```php
$user = tap($user)->update([
    'name' => $name,
    'email' => $email,
]);
```

To add a `tap` method to a class, you may add the `Illuminate\Support\Traits\Tappable` trait to the class. The `tap` method of this trait accepts a Closure as its only argument. The object instance itself will be passed to the Closure and then be returned by the `tap` method:

```php
return $user->tap(function ($user) {
    //
});
```

<a name="method-throw-if"></a>
#### `throw_if()`

The `throw_if` function throws the given exception if a given boolean expression evaluates to `true`:

```php
throw_if(! Auth::user()->isAdmin(), AuthorizationException::class);

throw_if(
    ! Auth::user()->isAdmin(),
    AuthorizationException::class,
    'You are not allowed to access this page.'
);
```

<a name="method-throw-unless"></a>
#### `throw_unless()`

The `throw_unless` function throws the given exception if a given boolean expression evaluates to `false`:

```php
throw_unless(Auth::user()->isAdmin(), AuthorizationException::class);

throw_unless(
    Auth::user()->isAdmin(),
    AuthorizationException::class,
    'You are not allowed to access this page.'
);
```

<a name="method-today"></a>
#### `today()`

The `today` function creates a new `Illuminate\Support\Carbon` instance for the current date:

```php
$today = today();
```

<a name="method-trait-uses-recursive"></a>
#### `trait_uses_recursive()`

The `trait_uses_recursive` function returns all traits used by a trait:

```php
$traits = trait_uses_recursive(\Illuminate\Notifications\Notifiable::class);
```

<a name="method-transform"></a>
#### `transform()`

The `transform` function executes a closure on a given value if the value is not [blank](#method-blank) and then returns the return value of the closure:

```php
$callback = function ($value) {
    return $value * 2;
};

$result = transform(5, $callback);

// 10
```

A default value or closure may be passed as the third argument to the function. This value will be returned if the given value is blank:

```php
$result = transform(null, $callback, 'The value is blank');

// The value is blank

```
<a name="method-validator"></a>
#### `validator()`

The `validator` function creates a new [validator](/docs/{{version}}/validation) instance with the given arguments. You may use it as an alternative to the `Validator` facade:

```php
$validator = validator($data, $rules, $messages);
```

<a name="method-value"></a>
#### `value()`

The `value` function returns the value it is given. However, if you pass a closure to the function, the closure will be executed and its returned value will be returned:

```php
$result = value(true);

// true

$result = value(function () {
    return false;
});

// false
```

<a name="method-view"></a>
#### `view()`

The `view` function retrieves a [view](/docs/{{version}}/views) instance:

```php
return view('auth.login');
```

<a name="method-with"></a>
#### `with()`

The `with` function returns the value it is given. If a closure is passed as the second argument to the function, the closure will be executed and its returned value will be returned:

```php
$callback = function ($value) {
    return is_numeric($value) ? $value * 2 : 0;
};

$result = with(5, $callback);

// 10

$result = with(null, $callback);

// 0

$result = with(5, null);

// 5
```
