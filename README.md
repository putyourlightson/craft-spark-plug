[![Stable Version](https://img.shields.io/packagist/v/putyourlightson/craft-spark-plug?label=stable)]((https://packagist.org/packages/putyourlightson/craft-spark-plug))
[![Total Downloads](https://img.shields.io/packagist/dt/putyourlightson/craft-spark-plug)](https://packagist.org/packages/putyourlightson/craft-spark-plug)

<p align="center"><img width="150" src="https://putyourlightson.com/assets/logos/spark-icon.svg"></p>

# Spark Plug Module for Craft CMS

This module provides the core functionality for the [Spark plugin](https://github.com/putyourlightson/craft-spark), real-time, template-driven hypermedia framework for [Craft CMS](https://craftcms.com/). If you are developing a Craft plugin/module and would like to use Spark in the control panel, then you can require this package to give you its functionality, without requiring that the site has the Spark plugin installed.

First require the package in your plugin/module's `composer.json` file.

```json
{
  "require": {
    "putyourlightson/craft-spark-plug": "^1.0.0-alpha.1"
  }
}
```

Then bootstrap the module from within your plugin/module's `init` method.

```php
use craft\base\Plugin;
use putyourlightson\spark\Spark;

class MyPlugin extends Plugin
{
    public function init()
    {
        parent::init();

        Spark::bootstrap();
    }
}
```

Then use the Spark function and tags as normal in your control panel templates.

```twig
<button data-on-click="{{ spark('_spark/search') }}">Search</button>
```

If your plugin/module registers an asset bundle that depends on Datastar being loaded, ensure that you specify the `DatastarAssetBundle` class as a dependency.

```php
use craft\web\AssetBundle;
use putyourlightson\spark\assets\DatastarAssetBundle;

class MyAssetBundle extends AssetBundle
{
    public $depends = [
        DatastarAssetBundle::class,
    ];
}
```

Spark plugin issues should be reported to https://github.com/putyourlightson/craft-spark/issues

Spark plugin changes are documented in https://github.com/putyourlightson/craft-spark/blob/develop/CHANGELOG.md

## Documentation

Learn more and read the documentation at [putyourlightson.com/plugins/spark »](https://putyourlightson.com/plugins/spark)

## License

This plugin is licensed for free under the MIT License.

## Requirements

This plugin requires [Craft CMS](https://craftcms.com/) 5.0.0 or later.

## Installation

Install this package via composer.

```shell
composer require putyourlightson/craft-spark-plug:^1.0.0-alpha.1
```

---

Created by [PutYourLightsOn](https://putyourlightson.com/).