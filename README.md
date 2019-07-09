Easily convert valid xml to a php array.

## Installation

Install via composer:

```
composer require Metawesome/xml-to-array
```

## Quick start

### Using the class

```php
use Metawesome\XmlToArray\XmlToArray;

$xml = <<<XML
<?xml version="1.0"?>
<request>
    <carrier>fedex</carrier>
    <id>123</id>
    <tracking_number>9205590164917312751089</tracking_number>
</request>
XML;

$array = XmlToArray::convert($xml);

// $array is:
[
	'carrier' => 'fedex',
	'id' => '123',
	'tracking_number' => '9205590164917312751089'
];

```

### Using the global helper

```php
$xml = <<<XML
<?xml version="1.0"?>
<request>
    <carrier>fedex</carrier>
    <id>123</id>
    <tracking_number>9205590164917312751089</tracking_number>
</request>
XML;

$array = xml_to_array($xml);

// $array is:
[
	'carrier' => 'fedex',
	'id' => '123',
	'tracking_number' => '9205590164917312751089'
];
```

## Helpers, methods, and arguments

**Static method**

``XmlToArray::convert($xml, $outputRoot = false)``

The ``$outputRoot`` determines whether or not the php array will have a ``@root`` key. Default is ``false``.

**Helper**

``xml_to_array($xml, $outputRoot = false)``

Arguments are identical to ``XmlToArray::convert`` method.

## Testing

You can run the tests with:

```bash
./vendor/bin/phpunit
```

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.