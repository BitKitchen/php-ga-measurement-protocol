Google Analytics Measurement Protocol PHP Client
===========================================================================================

[![Build Status](https://travis-ci.org/krizon/php-ga-measurement-protocol.png?branch=master)](https://travis-ci.org/krizon/php-ga-measurement-protocol)
[![Scrutinizer Quality Score](https://scrutinizer-ci.com/g/krizon/php-ga-measurement-protocol/badges/quality-score.png?s=690ba3465d629f9876678af9ae4a41a346c994ab)](https://scrutinizer-ci.com/g/krizon/php-ga-measurement-protocol/)
[![Code Coverage](https://scrutinizer-ci.com/g/krizon/php-ga-measurement-protocol/badges/coverage.png?s=17fc1b99fc85fec329329b96ecca1838fe3a5b7d)](https://scrutinizer-ci.com/g/krizon/php-ga-measurement-protocol/)
[![Latest Stable Version](https://poser.pugx.org/krizon/php-ga-measurement-protocol/v/stable.png)](https://packagist.org/packages/krizon/php-ga-measurement-protocol) [![Total Downloads](https://poser.pugx.org/krizon/php-ga-measurement-protocol/downloads.png)](https://packagist.org/packages/krizon/php-ga-measurement-protocol) [![Latest Unstable Version](https://poser.pugx.org/krizon/php-ga-measurement-protocol/v/unstable.png)](https://packagist.org/packages/krizon/php-ga-measurement-protocol) [![License](https://poser.pugx.org/krizon/php-ga-measurement-protocol/license.png)](https://packagist.org/packages/krizon/php-ga-measurement-protocol)

A full featured php client for the Google Analytics Measurment Protocol API. Build upon the shoulders of the great [Guzzle](http://docs.guzzlephp.org/en/latest/).

See https://developers.google.com/analytics/devguides/collection/protocol/v1/devguide

Installation
-------------------------------------------------------------------------------------------
Use [Composer](http://getcomposer.org/doc/00-intro.md) to add this library to your dependencies:
```bash
$ composer require krizon/php-ga-measurement-protocol
```

Features
-------------------------------------------------------------------------------------------
- Page tracking
- Event tracking
- Ecommerce tracking
- Social interactions tracking
- Exception tracking
- User timing tracking
- App tracking
- Non-blocking requests (todo)

Usage
-------------------------------------------------------------------------------------------
```php
$config = array(
    'ssl' => true // Enable/Disable SSL, default false
);
$client = Krizon\Google\Analytics\MeasurementProtocol\MeasurementProtocolClient::factory($config);
$client->pageview(array(
    'tid' => 'UA-XXXX-XXXX', // Tracking Id 
    'cid' => 'XXXX-XXXXX-XXXXX', // Customer Id
    'dh' => 'domain.do',
    'dp' => '/php-ga-measurement-protocol/phpunit-test',
    'dt' => 'PHP GA Measurement Protocol'
));
```

Testing
-------------------------------------------------------------------------------------------
Before you can run the tests make sure you installed the dependencies using composer:

```$ composer install```

PHPUnit itself is included in the dependencies so now you can call:

```$ vendor/bin/phpunit```

We have two types of tests:

* Tests with mocked 200 OK response, @group ```__nogroup__```. This type of tests are used tor testing required fields,
asserting classtypes etc.;
* Tests that do real calls to the Google API, @group ```internet```. The Google API itself always returns a 200 OK so to
be sure the requests are transferred and handled correctly you can run the tests of group 'internet'. Before running
this group make sure you've configured the correct tracking id in the phpunit.xml configuration by setting the env variable
```tracking_id```. This group is excluded by default but you can run this tests by calling:
```$ vendor/bin/phpunit --group internet```

Contributors
-------------------------------------------------------------------------------------------
* [Kristian Zondervan](https://github.com/krizon)
* [Alexandre Assouad](https://github.com/t0k4rt)
* [Matt Weghorst](https://github.com/mattweg)

