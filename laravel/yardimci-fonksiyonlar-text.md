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

<a name="fluent-strings-method-list"></a>
### Fluent Strings

<div class="collection-method-list" markdown="1">

[after](#method-fluent-str-after)
[afterLast](#method-fluent-str-after-last)
[append](#method-fluent-str-append)
[ascii](#method-fluent-str-ascii)
[basename](#method-fluent-str-basename)
[before](#method-fluent-str-before)
[beforeLast](#method-fluent-str-before-last)
[between](#method-fluent-str-between)
[betweenFirst](#method-fluent-str-between-first)
[camel](#method-fluent-str-camel)
[contains](#method-fluent-str-contains)
[containsAll](#method-fluent-str-contains-all)
[dirname](#method-fluent-str-dirname)
[endsWith](#method-fluent-str-ends-with)
[excerpt](#method-fluent-str-excerpt)
[exactly](#method-fluent-str-exactly)
[explode](#method-fluent-str-explode)
[finish](#method-fluent-str-finish)
[is](#method-fluent-str-is)
[isAscii](#method-fluent-str-is-ascii)
[isEmpty](#method-fluent-str-is-empty)
[isNotEmpty](#method-fluent-str-is-not-empty)
[isUuid](#method-fluent-str-is-uuid)
[kebab](#method-fluent-str-kebab)
[lcfirst](#method-fluent-str-lcfirst)
[length](#method-fluent-str-length)
[limit](#method-fluent-str-limit)
[lower](#method-fluent-str-lower)
[ltrim](#method-fluent-str-ltrim)
[markdown](#method-fluent-str-markdown)
[mask](#method-fluent-str-mask)
[match](#method-fluent-str-match)
[matchAll](#method-fluent-str-match-all)
[padBoth](#method-fluent-str-padboth)
[padLeft](#method-fluent-str-padleft)
[padRight](#method-fluent-str-padright)
[pipe](#method-fluent-str-pipe)
[plural](#method-fluent-str-plural)
[prepend](#method-fluent-str-prepend)
[remove](#method-fluent-str-remove)
[replace](#method-fluent-str-replace)
[replaceArray](#method-fluent-str-replace-array)
[replaceFirst](#method-fluent-str-replace-first)
[replaceLast](#method-fluent-str-replace-last)
[replaceMatches](#method-fluent-str-replace-matches)
[rtrim](#method-fluent-str-rtrim)
[scan](#method-fluent-str-scan)
[singular](#method-fluent-str-singular)
[slug](#method-fluent-str-slug)
[snake](#method-fluent-str-snake)
[split](#method-fluent-str-split)
[start](#method-fluent-str-start)
[startsWith](#method-fluent-str-starts-with)
[studly](#method-fluent-str-studly)
[substr](#method-fluent-str-substr)
[substrReplace](#method-fluent-str-substrreplace)
[swap](#method-fluent-str-swap)
[tap](#method-fluent-str-tap)
[test](#method-fluent-str-test)
[title](#method-fluent-str-title)
[trim](#method-fluent-str-trim)
[ucfirst](#method-fluent-str-ucfirst)
[upper](#method-fluent-str-upper)
[when](#method-fluent-str-when)
[whenContains](#method-fluent-str-when-contains)
[whenContainsAll](#method-fluent-str-when-contains-all)
[whenEmpty](#method-fluent-str-when-empty)
[whenNotEmpty](#method-fluent-str-when-not-empty)
[whenStartsWith](#method-fluent-str-when-starts-with)
[whenEndsWith](#method-fluent-str-when-ends-with)
[whenExactly](#method-fluent-str-when-exactly)
[whenIs](#method-fluent-str-when-is)
[whenIsAscii](#method-fluent-str-when-is-ascii)
[whenIsUuid](#method-fluent-str-when-is-uuid)
[whenTest](#method-fluent-str-when-test)
[wordCount](#method-fluent-str-word-count)
[words](#method-fluent-str-words)

</div>

<a name="fluent-strings"></a>
## Fluent Strings

Fluent strings provide a more fluent, object-oriented interface for working with string values, allowing you to chain multiple string operations together using a more readable syntax compared to traditional string operations.

<a name="method-fluent-str-after"></a>
#### `after`

The `after` method returns everything after the given value in a string. The entire string will be returned if the value does not exist within the string:

    use Illuminate\Support\Str;

    $slice = Str::of('This is my name')->after('This is');

    // ' my name'

<a name="method-fluent-str-after-last"></a>
#### `afterLast`

The `afterLast` method returns everything after the last occurrence of the given value in a string. The entire string will be returned if the value does not exist within the string:

    use Illuminate\Support\Str;

    $slice = Str::of('App\Http\Controllers\Controller')->afterLast('\\');

    // 'Controller'

<a name="method-fluent-str-append"></a>
#### `append`

The `append` method appends the given values to the string:

    use Illuminate\Support\Str;

    $string = Str::of('Taylor')->append(' Otwell');

    // 'Taylor Otwell'

<a name="method-fluent-str-ascii"></a>
#### `ascii`

The `ascii` method will attempt to transliterate the string into an ASCII value:

    use Illuminate\Support\Str;

    $string = Str::of('ü')->ascii();

    // 'u'

<a name="method-fluent-str-basename"></a>
#### `basename`

The `basename` method will return the trailing name component of the given string:

    use Illuminate\Support\Str;

    $string = Str::of('/foo/bar/baz')->basename();

    // 'baz'

If needed, you may provide an "extension" that will be removed from the trailing component:

    use Illuminate\Support\Str;

    $string = Str::of('/foo/bar/baz.jpg')->basename('.jpg');

    // 'baz'

<a name="method-fluent-str-before"></a>
#### `before`

The `before` method returns everything before the given value in a string:

    use Illuminate\Support\Str;

    $slice = Str::of('This is my name')->before('my name');

    // 'This is '

<a name="method-fluent-str-before-last"></a>
#### `beforeLast`

The `beforeLast` method returns everything before the last occurrence of the given value in a string:

    use Illuminate\Support\Str;

    $slice = Str::of('This is my name')->beforeLast('is');

    // 'This '

<a name="method-fluent-str-between"></a>
#### `between`

The `between` method returns the portion of a string between two values:

    use Illuminate\Support\Str;

    $converted = Str::of('This is my name')->between('This', 'name');

    // ' is my '
    
<a name="method-fluent-str-between-first"></a>
#### `betweenFirst`

The `betweenFirst` method returns the smallest possible portion of a string between two values:

    use Illuminate\Support\Str;

    $converted = Str::of('[a] bc [d]')->betweenFirst('[', ']');

    // 'a'

<a name="method-fluent-str-camel"></a>
#### `camel`

The `camel` method converts the given string to `camelCase`:

    use Illuminate\Support\Str;

    $converted = Str::of('foo_bar')->camel();

    // fooBar

<a name="method-fluent-str-contains"></a>
#### `contains`

The `contains` method determines if the given string contains the given value. This method is case sensitive:

    use Illuminate\Support\Str;

    $contains = Str::of('This is my name')->contains('my');

    // true

You may also pass an array of values to determine if the given string contains any of the values in the array:

    use Illuminate\Support\Str;

    $contains = Str::of('This is my name')->contains(['my', 'foo']);

    // true

<a name="method-fluent-str-contains-all"></a>
#### `containsAll`

The `containsAll` method determines if the given string contains all of the values in the given array:

    use Illuminate\Support\Str;

    $containsAll = Str::of('This is my name')->containsAll(['my', 'name']);

    // true

<a name="method-fluent-str-dirname"></a>
#### `dirname`

The `dirname` method returns the parent directory portion of the given string:

    use Illuminate\Support\Str;

    $string = Str::of('/foo/bar/baz')->dirname();

    // '/foo/bar'

If necessary, you may specify how many directory levels you wish to trim from the string:

    use Illuminate\Support\Str;

    $string = Str::of('/foo/bar/baz')->dirname(2);

    // '/foo'

<a name="method-fluent-str-excerpt"></a>
#### `excerpt`

The `excerpt` method extracts an excerpt from the string that matches the first instance of a phrase within that string:

    use Illuminate\Support\Str;

    $excerpt = Str::of('This is my name')->excerpt('my', [
        'radius' => 3
    ]);

    // '...is my na...'

The `radius` option, which defaults to `100`, allows you to define the number of characters that should appear on each side of the truncated string.

In addition, you may use the `omission` option to change the string that will be prepended and appended to the truncated string:

    use Illuminate\Support\Str;

    $excerpt = Str::of('This is my name')->excerpt('name', [
        'radius' => 3,
        'omission' => '(...) '
    ]);

    // '(...) my name'

<a name="method-fluent-str-ends-with"></a>
#### `endsWith`

The `endsWith` method determines if the given string ends with the given value:

    use Illuminate\Support\Str;

    $result = Str::of('This is my name')->endsWith('name');

    // true

You may also pass an array of values to determine if the given string ends with any of the values in the array:

    use Illuminate\Support\Str;

    $result = Str::of('This is my name')->endsWith(['name', 'foo']);

    // true

    $result = Str::of('This is my name')->endsWith(['this', 'foo']);

    // false

<a name="method-fluent-str-exactly"></a>
#### `exactly`

The `exactly` method determines if the given string is an exact match with another string:

    use Illuminate\Support\Str;

    $result = Str::of('Laravel')->exactly('Laravel');

    // true

<a name="method-fluent-str-explode"></a>
#### `explode`

The `explode` method splits the string by the given delimiter and returns a collection containing each section of the split string:

    use Illuminate\Support\Str;

    $collection = Str::of('foo bar baz')->explode(' ');

    // collect(['foo', 'bar', 'baz'])

<a name="method-fluent-str-finish"></a>
#### `finish`

The `finish` method adds a single instance of the given value to a string if it does not already end with that value:

    use Illuminate\Support\Str;

    $adjusted = Str::of('this/string')->finish('/');

    // this/string/

    $adjusted = Str::of('this/string/')->finish('/');

    // this/string/

<a name="method-fluent-str-is"></a>
#### `is`

The `is` method determines if a given string matches a given pattern. Asterisks may be used as wildcard values

    use Illuminate\Support\Str;

    $matches = Str::of('foobar')->is('foo*');

    // true

    $matches = Str::of('foobar')->is('baz*');

    // false

<a name="method-fluent-str-is-ascii"></a>
#### `isAscii`

The `isAscii` method determines if a given string is an ASCII string:

    use Illuminate\Support\Str;

    $result = Str::of('Taylor')->isAscii();

    // true

    $result = Str::of('ü')->isAscii();

    // false

<a name="method-fluent-str-is-empty"></a>
#### `isEmpty`

The `isEmpty` method determines if the given string is empty:

    use Illuminate\Support\Str;

    $result = Str::of('  ')->trim()->isEmpty();

    // true

    $result = Str::of('Laravel')->trim()->isEmpty();

    // false

<a name="method-fluent-str-is-not-empty"></a>
#### `isNotEmpty`

The `isNotEmpty` method determines if the given string is not empty:


    use Illuminate\Support\Str;

    $result = Str::of('  ')->trim()->isNotEmpty();

    // false

    $result = Str::of('Laravel')->trim()->isNotEmpty();

    // true

<a name="method-fluent-str-is-uuid"></a>
#### `isUuid`

The `isUuid` method determines if a given string is a UUID:

    use Illuminate\Support\Str;

    $result = Str::of('5ace9ab9-e9cf-4ec6-a19d-5881212a452c')->isUuid();

    // true

    $result = Str::of('Taylor')->isUuid();

    // false

<a name="method-fluent-str-kebab"></a>
#### `kebab`

The `kebab` method converts the given string to `kebab-case`:

    use Illuminate\Support\Str;

    $converted = Str::of('fooBar')->kebab();

    // foo-bar
    
<a name="method-str-fluent-lcfirst"></a>
#### `lcfirst()`

The `lcfirst` method returns the given string with the first character lowercased:

    use Illuminate\Support\Str;

    $string = Str::of('Foo Bar')->lcfirst();

    // foo Bar


<a name="method-fluent-str-length"></a>
#### `length`

The `length` method returns the length of the given string:

    use Illuminate\Support\Str;

    $length = Str::of('Laravel')->length();

    // 7

<a name="method-fluent-str-limit"></a>
#### `limit`

The `limit` method truncates the given string to the specified length:

    use Illuminate\Support\Str;

    $truncated = Str::of('The quick brown fox jumps over the lazy dog')->limit(20);

    // The quick brown fox...

You may also pass a second argument to change the string that will be appended to the end of the truncated string:

    use Illuminate\Support\Str;

    $truncated = Str::of('The quick brown fox jumps over the lazy dog')->limit(20, ' (...)');

    // The quick brown fox (...)

<a name="method-fluent-str-lower"></a>
#### `lower`

The `lower` method converts the given string to lowercase:

    use Illuminate\Support\Str;

    $result = Str::of('LARAVEL')->lower();

    // 'laravel'

<a name="method-fluent-str-ltrim"></a>
#### `ltrim`

The `ltrim` method trims the left side of the string:

    use Illuminate\Support\Str;

    $string = Str::of('  Laravel  ')->ltrim();

    // 'Laravel  '

    $string = Str::of('/Laravel/')->ltrim('/');

    // 'Laravel/'

<a name="method-fluent-str-markdown"></a>
#### `markdown`

The `markdown` method converts GitHub flavored Markdown into HTML:

    use Illuminate\Support\Str;

    $html = Str::of('# Laravel')->markdown();

    // <h1>Laravel</h1>

    $html = Str::of('# Taylor <b>Otwell</b>')->markdown([
        'html_input' => 'strip',
    ]);

    // <h1>Taylor Otwell</h1>

<a name="method-fluent-str-mask"></a>
#### `mask`

The `mask` method masks a portion of a string with a repeated character, and may be used to obfuscate segments of strings such as email addresses and phone numbers:

    use Illuminate\Support\Str;

    $string = Str::of('taylor@example.com')->mask('*', 3);

    // tay***************

If needed, you provide a negative number as the third argument to the `mask` method, which will instruct the method to begin masking at the given distance from the end of the string:

    $string = Str::of('taylor@example.com')->mask('*', -15, 3);

    // tay***@example.com

<a name="method-fluent-str-match"></a>
#### `match`

The `match` method will return the portion of a string that matches a given regular expression pattern:

    use Illuminate\Support\Str;

    $result = Str::of('foo bar')->match('/bar/');

    // 'bar'

    $result = Str::of('foo bar')->match('/foo (.*)/');

    // 'bar'

<a name="method-fluent-str-match-all"></a>
#### `matchAll`

The `matchAll` method will return a collection containing the portions of a string that match a given regular expression pattern:

    use Illuminate\Support\Str;

    $result = Str::of('bar foo bar')->matchAll('/bar/');

    // collect(['bar', 'bar'])

If you specify a matching group within the expression, Laravel will return a collection of that group's matches:

    use Illuminate\Support\Str;

    $result = Str::of('bar fun bar fly')->matchAll('/f(\w*)/');

    // collect(['un', 'ly']);

If no matches are found, an empty collection will be returned.

<a name="method-fluent-str-padboth"></a>
#### `padBoth`

The `padBoth` method wraps PHP's `str_pad` function, padding both sides of a string with another string until the final string reaches the desired length:

    use Illuminate\Support\Str;

    $padded = Str::of('James')->padBoth(10, '_');

    // '__James___'

    $padded = Str::of('James')->padBoth(10);

    // '  James   '

<a name="method-fluent-str-padleft"></a>
#### `padLeft`

The `padLeft` method wraps PHP's `str_pad` function, padding the left side of a string with another string until the final string reaches the desired length:

    use Illuminate\Support\Str;

    $padded = Str::of('James')->padLeft(10, '-=');

    // '-=-=-James'

    $padded = Str::of('James')->padLeft(10);

    // '     James'

<a name="method-fluent-str-padright"></a>
#### `padRight`

The `padRight` method wraps PHP's `str_pad` function, padding the right side of a string with another string until the final string reaches the desired length:

    use Illuminate\Support\Str;

    $padded = Str::of('James')->padRight(10, '-');

    // 'James-----'

    $padded = Str::of('James')->padRight(10);

    // 'James     '

<a name="method-fluent-str-pipe"></a>
#### `pipe`

The `pipe` method allows you to transform the string by passing its current value to the given callable:

    use Illuminate\Support\Str;

    $hash = Str::of('Laravel')->pipe('md5')->prepend('Checksum: ');

    // 'Checksum: a5c95b86291ea299fcbe64458ed12702'

    $closure = Str::of('foo')->pipe(function ($str) {
        return 'bar';
    });

    // 'bar'

<a name="method-fluent-str-plural"></a>
#### `plural`

The `plural` method converts a singular word string to its plural form. This function currently only supports the English language:

    use Illuminate\Support\Str;

    $plural = Str::of('car')->plural();

    // cars

    $plural = Str::of('child')->plural();

    // children

You may provide an integer as a second argument to the function to retrieve the singular or plural form of the string:

    use Illuminate\Support\Str;

    $plural = Str::of('child')->plural(2);

    // children

    $plural = Str::of('child')->plural(1);

    // child

<a name="method-fluent-str-prepend"></a>
#### `prepend`

The `prepend` method prepends the given values onto the string:

    use Illuminate\Support\Str;

    $string = Str::of('Framework')->prepend('Laravel ');

    // Laravel Framework

<a name="method-fluent-str-remove"></a>
#### `remove`

The `remove` method removes the given value or array of values from the string:

    use Illuminate\Support\Str;

    $string = Str::of('Arkansas is quite beautiful!')->remove('quite');

    // Arkansas is beautiful!

You may also pass `false` as a second parameter to ignore case when removing strings.

<a name="method-fluent-str-replace"></a>
#### `replace`

The `replace` method replaces a given string within the string:

    use Illuminate\Support\Str;

    $replaced = Str::of('Laravel 6.x')->replace('6.x', '7.x');

    // Laravel 7.x

<a name="method-fluent-str-replace-array"></a>
#### `replaceArray`

The `replaceArray` method replaces a given value in the string sequentially using an array:

    use Illuminate\Support\Str;

    $string = 'The event will take place between ? and ?';

    $replaced = Str::of($string)->replaceArray('?', ['8:30', '9:00']);

    // The event will take place between 8:30 and 9:00

<a name="method-fluent-str-replace-first"></a>
#### `replaceFirst`

The `replaceFirst` method replaces the first occurrence of a given value in a string:

    use Illuminate\Support\Str;

    $replaced = Str::of('the quick brown fox jumps over the lazy dog')->replaceFirst('the', 'a');

    // a quick brown fox jumps over the lazy dog

<a name="method-fluent-str-replace-last"></a>
#### `replaceLast`

The `replaceLast` method replaces the last occurrence of a given value in a string:

    use Illuminate\Support\Str;

    $replaced = Str::of('the quick brown fox jumps over the lazy dog')->replaceLast('the', 'a');

    // the quick brown fox jumps over a lazy dog

<a name="method-fluent-str-replace-matches"></a>
#### `replaceMatches`

The `replaceMatches` method replaces all portions of a string matching a pattern with the given replacement string:

    use Illuminate\Support\Str;

    $replaced = Str::of('(+1) 501-555-1000')->replaceMatches('/[^A-Za-z0-9]++/', '')

    // '15015551000'

The `replaceMatches` method also accepts a closure that will be invoked with each portion of the string matching the given pattern, allowing you to perform the replacement logic within the closure and return the replaced value:

    use Illuminate\Support\Str;

    $replaced = Str::of('123')->replaceMatches('/\d/', function ($match) {
        return '['.$match[0].']';
    });

    // '[1][2][3]'

<a name="method-fluent-str-rtrim"></a>
#### `rtrim`

The `rtrim` method trims the right side of the given string:

    use Illuminate\Support\Str;

    $string = Str::of('  Laravel  ')->rtrim();

    // '  Laravel'

    $string = Str::of('/Laravel/')->rtrim('/');

    // '/Laravel'

<a name="method-fluent-str-scan"></a>
#### `scan`

The `scan` method parses input from a string into a collection according to a format supported by the [`sscanf` PHP function](https://www.php.net/manual/en/function.sscanf.php):

    use Illuminate\Support\Str;

    $collection = Str::of('filename.jpg')->scan('%[^.].%s');

    // collect(['filename', 'jpg'])

<a name="method-fluent-str-singular"></a>
#### `singular`

The `singular` method converts a string to its singular form. This function currently only supports the English language:

    use Illuminate\Support\Str;

    $singular = Str::of('cars')->singular();

    // car

    $singular = Str::of('children')->singular();

    // child

<a name="method-fluent-str-slug"></a>
#### `slug`

The `slug` method generates a URL friendly "slug" from the given string:

    use Illuminate\Support\Str;

    $slug = Str::of('Laravel Framework')->slug('-');

    // laravel-framework

<a name="method-fluent-str-snake"></a>
#### `snake`

The `snake` method converts the given string to `snake_case`:

    use Illuminate\Support\Str;

    $converted = Str::of('fooBar')->snake();

    // foo_bar

<a name="method-fluent-str-split"></a>
#### `split`

The `split` method splits a string into a collection using a regular expression:

    use Illuminate\Support\Str;

    $segments = Str::of('one, two, three')->split('/[\s,]+/');

    // collect(["one", "two", "three"])

<a name="method-fluent-str-start"></a>
#### `start`

The `start` method adds a single instance of the given value to a string if it does not already start with that value:

    use Illuminate\Support\Str;

    $adjusted = Str::of('this/string')->start('/');

    // /this/string

    $adjusted = Str::of('/this/string')->start('/');

    // /this/string

<a name="method-fluent-str-starts-with"></a>
#### `startsWith`

The `startsWith` method determines if the given string begins with the given value:

    use Illuminate\Support\Str;

    $result = Str::of('This is my name')->startsWith('This');

    // true

<a name="method-fluent-str-studly"></a>
#### `studly`

The `studly` method converts the given string to `StudlyCase`:

    use Illuminate\Support\Str;

    $converted = Str::of('foo_bar')->studly();

    // FooBar

<a name="method-fluent-str-substr"></a>
#### `substr`

The `substr` method returns the portion of the string specified by the given start and length parameters:

    use Illuminate\Support\Str;

    $string = Str::of('Laravel Framework')->substr(8);

    // Framework

    $string = Str::of('Laravel Framework')->substr(8, 5);

    // Frame

<a name="method-fluent-str-substrreplace"></a>
#### `substrReplace`

The `substrReplace` method replaces text within a portion of a string, starting at the position specified by the second argument and replacing the number of characters specified by the third argument. Passing `0` to the method's third argument will insert the string at the specified position without replacing any of the existing characters in the string:

    use Illuminate\Support\Str;

    $string = Str::of('1300')->substrReplace(':', 2);

    // 13:

    $string = Str::of('The Framework')->substrReplace(' Laravel', 3, 0);

    // The Laravel Framework

<a name="method-fluent-str-swap"></a>
#### `swap`

The `swap` method replaces multiple values in the string using PHP's `strtr` function:

    use Illuminate\Support\Str;

    $string = Str::of('Tacos are great!')
        ->swap([
            'Tacos' => 'Burritos',
            'great' => 'fantastic',
        ]);

    // Burritos are fantastic!

<a name="method-fluent-str-tap"></a>
#### `tap`

The `tap` method passes the string to the given closure, allowing you to examine and interact with the string while not affecting the string itself. The original string is returned by the `tap` method regardless of what is returned by the closure:

    use Illuminate\Support\Str;

    $string = Str::of('Laravel')
        ->append(' Framework')
        ->tap(function ($string) {
            dump('String after append: ' . $string);
        })
        ->upper();

    // LARAVEL FRAMEWORK

<a name="method-fluent-str-test"></a>
#### `test`

The `test` method determines if a string matches the given regular expression pattern:

    use Illuminate\Support\Str;

    $result = Str::of('Laravel Framework')->test('/Laravel/');

    // true

<a name="method-fluent-str-title"></a>
#### `title`

The `title` method converts the given string to `Title Case`:

    use Illuminate\Support\Str;

    $converted = Str::of('a nice title uses the correct case')->title();

    // A Nice Title Uses The Correct Case

<a name="method-fluent-str-trim"></a>
#### `trim`

The `trim` method trims the given string:

    use Illuminate\Support\Str;

    $string = Str::of('  Laravel  ')->trim();

    // 'Laravel'

    $string = Str::of('/Laravel/')->trim('/');

    // 'Laravel'

<a name="method-fluent-str-ucfirst"></a>
#### `ucfirst`

The `ucfirst` method returns the given string with the first character capitalized:

    use Illuminate\Support\Str;

    $string = Str::of('foo bar')->ucfirst();

    // Foo bar

<a name="method-fluent-str-upper"></a>
#### `upper`

The `upper` method converts the given string to uppercase:

    use Illuminate\Support\Str;

    $adjusted = Str::of('laravel')->upper();

    // LARAVEL

<a name="method-fluent-str-when"></a>
#### `when`

The `when` method invokes the given closure if a given condition is `true`. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('Taylor')
                    ->when(true, function ($string) {
                        return $string->append(' Otwell');
                    });

    // 'Taylor Otwell'

If necessary, you may pass another closure as the third parameter to the `when` method. This closure will execute if the condition parameter evaluates to `false`.

<a name="method-fluent-str-when-contains"></a>
#### `whenContains`

The `whenContains` method invokes the given closure if the string contains the given value. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('tony stark')
                ->whenContains('tony', function ($string) {
                    return $string->title();
                });

    // 'Tony Stark'

If necessary, you may pass another closure as the third parameter to the `when` method. This closure will execute if the string does not contain the given value.

You may also pass an array of values to determine if the given string contains any of the values in the array:

    use Illuminate\Support\Str;

    $string = Str::of('tony stark')
                ->whenContains(['tony', 'hulk'], function ($string) {
                    return $string->title();
                });

    // Tony Stark

<a name="method-fluent-str-when-contains-all"></a>
#### `whenContainsAll`

The `whenContainsAll` method invokes the given closure if the string contains all of the given sub-strings. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('tony stark')
                    ->whenContainsAll(['tony', 'stark'], function ($string) {
                        return $string->title();
                    });

    // 'Tony Stark'

If necessary, you may pass another closure as the third parameter to the `when` method. This closure will execute if the condition parameter evaluates to `false`.

<a name="method-fluent-str-when-empty"></a>
#### `whenEmpty`

The `whenEmpty` method invokes the given closure if the string is empty. If the closure returns a value, that value will also be returned by the `whenEmpty` method. If the closure does not return a value, the fluent string instance will be returned:

    use Illuminate\Support\Str;

    $string = Str::of('  ')->whenEmpty(function ($string) {
        return $string->trim()->prepend('Laravel');
    });

    // 'Laravel'

<a name="method-fluent-str-when-not-empty"></a>
#### `whenNotEmpty`

The `whenNotEmpty` method invokes the given closure if the string is not empty. If the closure returns a value, that value will also be returned by the `whenNotEmpty` method. If the closure does not return a value, the fluent string instance will be returned:

    use Illuminate\Support\Str;

    $string = Str::of('Framework')->whenNotEmpty(function ($string) {
        return $string->prepend('Laravel ');
    });

    // 'Laravel Framework'

<a name="method-fluent-str-when-starts-with"></a>
#### `whenStartsWith`

The `whenStartsWith` method invokes the given closure if the string starts with the given sub-string. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('disney world')->whenStartsWith('disney', function ($string) {
        return $string->title();
    });

    // 'Disney World'

<a name="method-fluent-str-when-ends-with"></a>
#### `whenEndsWith`

The `whenEndsWith` method invokes the given closure if the string ends with the given sub-string. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('disney world')->whenEndsWith('world', function ($string) {
        return $string->title();
    });

    // 'Disney World'

<a name="method-fluent-str-when-exactly"></a>
#### `whenExactly`

The `whenExactly` method invokes the given closure if the string exactly matches the given string. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('laravel')->whenExactly('laravel', function ($string) {
        return $string->title();
    });

    // 'Laravel'

<a name="method-fluent-str-when-is"></a>
#### `whenIs`

The `whenIs` method invokes the given closure if the string matches a given pattern. Asterisks may be used as wildcard values. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('foo/bar')->whenIs('foo/*', function ($string) {
        return $string->append('/baz');
    });

    // 'foo/bar/baz'

<a name="method-fluent-str-when-is-ascii"></a>
#### `whenIsAscii`

The `whenIsAscii` method invokes the given closure if the string is 7 bit ASCII. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('foo/bar')->whenIsAscii('laravel', function ($string) {
        return $string->title();
    });

    // 'Laravel'

<a name="method-fluent-str-when-is-uuid"></a>
#### `whenIsUuid`

The `whenIsUuid` method invokes the given closure if the string is a valid UUID. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('foo/bar')->whenIsUuid('a0a2a2d2-0b87-4a18-83f2-2529882be2de', function ($string) {
        return $string->substr(0, 8);
    });

    // 'a0a2a2d2'

<a name="method-fluent-str-when-test"></a>
#### `whenTest`

The `whenTest` method invokes the given closure if the string matches the given regular expression. The closure will receive the fluent string instance:

    use Illuminate\Support\Str;

    $string = Str::of('laravel framework')->whenTest('/laravel/', function ($string) {
        return $string->title();
    });

    // 'Laravel Framework'

<a name="method-fluent-str-word-count"></a>
#### `wordCount`

The `wordCount` method returns the number of words that a string contains:

```php
use Illuminate\Support\Str;

Str::of('Hello, world!')->wordCount(); // 2
```

<a name="method-fluent-str-words"></a>
#### `words`

The `words` method limits the number of words in a string. If necessary, you may specify an additional string that will be appended to the truncated string:

    use Illuminate\Support\Str;

    $string = Str::of('Perfectly balanced, as all things should be.')->words(3, ' >>>');

    // Perfectly balanced, as >>>
