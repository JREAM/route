# Route
***

I made this in 2011, it is a no-nonsense PHP Router. It
requires no dependencies. Fork it and have fun with it.

This is a class with two methods! I figured I'd port this over from
my old repositories. There are a thousand routers, all and everything
built into frameworks -- sometimes it's fun to go back to the basics.

This project was Inspired by [Klein](https://github.com/chriso/klein.php)

## Requirements

You need `PHP 5.3` or higher.

## How to use

You only need two files:

- 1: `route.php`
- 2: `.htaccess`

The `.htaccess` redirects all requests to `index.php?uri=$`.

You can run everything from the index.php file, see the file for usage.

## Examples

Require the route.php file and create an instance.
```php
require_once 'route.php';

$route = new Route();
```

Here is how you'd add your home page.

```php
$route->add('/', function() {
  echo 'This is the home page, there is no template engine';
});
```

Here is how to add arguments

```php
$route->add('/name/.+/age/.+', function($name, $age) {
  echo "Your name is $name and you are $age years old";
});
```

After all routes are defined, you always end it with:

```php
$route->listen();
```

***

Copyright (C), 2012 Jesse Boyer (<http://jream.com>)
GNU General Public License 3 (<http://www.gnu.org/licenses/>)
