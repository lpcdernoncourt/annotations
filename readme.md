## Annotations for The Laravel Framework

To Laravel 5.5

[![Build Status](https://travis-ci.org/lpcdernoncourt/annotations.svg)](https://travis-ci.org/lpcdernoncourt/annotations)
[![Total Downloads](https://poser.pugx.org/lpcdernoncourt/annotations/downloads)](https://packagist.org/packages/lpcdernoncourt/annotations)
[![Latest Stable Version](https://poser.pugx.org/lpcdernoncourt/annotations/v/stable.svg)](https://packagist.org/packages/lpcdernoncourt/annotations)
[![Latest Unstable Version](https://poser.pugx.org/lpcdernoncourt/annotations/v/unstable.svg)](https://packagist.org/packages/lpcdernoncourt/annotations)
[![License](https://poser.pugx.org/lpcdernoncourt/annotations/license.svg)](https://packagist.org/packages/lpcdernoncourt/annotations)

Official documentation for Annotations for The Laravel Framework can be found at the [LaravelCollective](http://laravelcollective.com) website.

## Installation

Add Presenter to your composer.json file:

```js
"require": {
    "lpcdernoncourt/annotations": "5.5.*"
}
```
Now, run a composer update on the command line from the root of your project:

```
composer update
```
Once composer is done, you'll need to create a Service Provider in app/Providers/AnnotationsServiceProvider.php.
```php
<?php namespace App\Providers;

use Collective\Annotations\AnnotationsServiceProvider as ServiceProvider;

class AnnotationsServiceProvider extends ServiceProvider {

    /**
     * The classes to scan for event annotations.
     *
     * @var array
     */
    protected $scanEvents = [];

    /**
     * The classes to scan for route annotations.
     *
     * @var array
     */
    protected $scanRoutes = [];

    /**
     * The classes to scan for model annotations.
     *
     * @var array
     */
    protected $scanModels = [];

    /**
     * Determines if we will auto-scan in the local environment.
     *
     * @var bool
     */
    protected $scanWhenLocal = false;

    /**
     * Determines whether or not to automatically scan the controllers
     * directory (App\Http\Controllers) for routes
     *
     * @var bool
     */
    protected $scanControllers = false;

    /**
     * Determines whether or not to automatically scan all namespaced
     * classes for event, route, and model annotations.
     *
     * @var bool
     */
    protected $scanEverything = false;

}
```
### Registering the Package

Include the service provider within `app/config/app.php`. The service povider is needed for the generator artisan command.

```php
'providers' => [
    // ...
    App\Providers\AnnotationsServiceProvider::class
    // ...
  ];
```

