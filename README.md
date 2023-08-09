 # Larasupport Package

> **Laravel Package Support for Lumen:** Makes Lumen compatible with Laravel Packages. You can use any Laravel Packages in Lumen by installing **Larasupport** Package.
>
> Laravel Packages make use of various global helpers that are not available in Lumen core by default which prevents us from using any Laravel Package in Lumen.
>
> This package adds the missing pieces to make Lumen compatible along with the support for `vendor:publish` artisan command and other features.  

## Quick Start

### Install

You can add the package directly by firing this command

```bash
$ composer require vinothvipin/lumenArtisanService
```

#### Add Service Provider

Add this service provider to your `bootstrap/app.php` file.

``` php
$app->register(vinothvipin\lumenArtisanService\Providers\ArtisanServiceProvider::class);
```

Artisan Service Provider is an optional provider required only if you want `vendor:publish` command working.

And you're done! You can now start installing any Laravel Package out there :)

## Available Methods

> These helpers can be used across your Lumen project, not only with Laravel Packages.

### Paths

#### app_path

Get the fully qualified path to the `app` directory.

#### public_path

Get the fully qualified path to the `public` directory. You can set env variable `PUBLIC_PATH` and it'll return the same instead of the default `public`.

#### config_path

Get the fully qualified path to the `config` directory (Mostly used with Laravel Packages).

### Artisan

#### vendor:publish

Artisan command to Publish any publishable assets from vendor packages (Required to get Laravel Packages working!).

``` bash
php artisan vendor:publish
```
OR

``` bash
php artisan vendor:publish --provider="Vendor\Providers\PackageServiceProvider" 
```

### Other

#### route_parameter

``` php
route_parameter($name, $default = null)
```

Get a given parameter from the route.
 
