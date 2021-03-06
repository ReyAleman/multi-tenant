[![Packagist](https://img.shields.io/packagist/v/hyn/multi-tenant.svg)]()
[![build status](https://gitlab.com/hyn-me/multi-tenant/badges/3.x/build.svg)](https://gitlab.com/hyn-me/multi-tenant/commits/3.x)
[![codecov](https://codecov.io/gh/hyn/multi-tenant/branch/3.x/graph/badge.svg)](https://codecov.io/gh/hyn/multi-tenant/branch/3.x)
[![Packagist](https://img.shields.io/packagist/dt/hyn/multi-tenant.svg)]()

## Requirements, recommended environment

- PHP 7.1+
- Apache 2.4+, nginx support coming soon.
- MariaDB 10+ or PostgreSQL 9+; please note that MySQL won't work because it limits database usernames to 16 characters.

## Installation

Register the service provider in your `config/app.php`:

```php
    'providers' => [
        // [..]
        // Hyn multi tenancy.
        Hyn\Tenancy\Providers\TenancyProvider::class,
        // Hyn multi tenancy webserver integration.
        Hyn\Tenancy\Providers\WebserverProvider::class,
    ],
```

First publish the configuration files so you can modify it to your needs:

```bash
php artisan vendor:deploy --tag tenancy
```

Open the `config/tenancy.php` and `config/webserver.php` file and modify to your needs.

Now run:

```bash
php artisan tenancy:install
```
This will run the required system database migrations.
