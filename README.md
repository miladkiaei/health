# Laravel Health Panel And Notifier

[![Latest Stable Version](https://img.shields.io/packagist/v/pragmarx/health.svg?style=flat-square)](https://packagist.org/packages/pragmarx/health) [![License](https://img.shields.io/badge/license-BSD_3_Clause-brightgreen.svg?style=flat-square)](LICENSE) [![Downloads](https://img.shields.io/packagist/dt/pragmarx/health.svg?style=flat-square)](https://packagist.org/packages/pragmarx/health)

This package creates a service status panel for you any Laravel app and has the follwing main points:
 
- Highly extendable and configurable: you can create new checkers and notifiers very easily, and you can virtually change everything on it.
- Built-in notification system: get notifications via mail, slack, telegram or anything else you need.
- Resilient: if the framework is working and at least one notification channel, you should receive notification messages. 
- Routes for: panel, json result, string result and resource.
- Configurable panel design.
- View app error messages right in the panel.
- Http response codes 200 and 500, for error states, to ease services like [Envoyer](https://envoyer.io) to keep track of your app health.

## Screenshots 

### Panel

![default panel](docs/images/error-multi.png)

### Panel alternate design

If you have lots of services to check, you may change the default panel design to use less space:

![default panel](docs/images/error-single-2-columns.png)

### Panel in 4 columns layout

![default panel](docs/images/error-single-4-columns.png)

### Error Messages 

Mouse over a failing resource and get instant access to the error message:

![default panel](docs/images/error-hint.png)

Click the resource button and you'll get an alert showing the error message:

![default panel](docs/images/error-alert.png)

### Slack Notification

![default panel](docs/images/slack.png)

## Routes

## Requirements

After installing you will have access to the folowing routes:

### /health/panel

The main panel route.

### /health/check

Returns a json with everything the package knows about your services:

![default panel](docs/images/json.png)

### /health/string

Returns a string with status on all your services, useful when using other monitoring services:

```
hlthFAIL-dbFAIL-filesystemOK-frmwrkOK-httpOK-httpsOK-mailOK
```

### /health/resource/{name}

Returns a json with information about a particular service:

![default panel](docs/images/json-resource.png)

## Requirements

- PHP 5.6+
- Laravel 5.2+

## Installing

Use Composer to install it:

    composer require pragmarx/health

## Installing on Laravel

Add the Service Provider and Facade alias to your `app/config/app.php` (Laravel 4.x) or `config/app.php` (Laravel 5.x):

    PragmaRX\Health\ServiceProvider::class,

## Publish config and views

    php artisan vendor:publish

## Configure All The Things

- Panel
- Title and messages
- Resource checkers
- Slack icon
- Sort resources in the panel
- Notification channels
- Template location
- Routes and prefixes
- Mail server

## Author

[Antonio Carlos Ribeiro](http://twitter.com/iantonioribeiro)

## License

Health is licensed under the BSD 3-Clause License - see the `LICENSE` file for details

## Contributing

Pull requests and issues are more than welcome.
