# WWPass API for multifactor authentication and data access

Composer-compliant WWPass API client library.

For single-file non-composer library please refer to [https://github.com/wwpass/wwpass-php-sdk](https://github.com/wwpass/wwpass-php-sdk).

## Installation

```bash
$ composer require wwpass/apiclient
```

## Usage

The library defines two classes in the WWPass namespace: **WWPass\Connection** and **WWPass\Exception**.

```php
require_once 'vendor/autoload.php';

try {
    $wwc = new WWPass\Connection(array(
        'key_file' => WWPASS_SPFE_KEY_FILE,
        'cert_file' => WWPASS_SPFE_CERT_FILE,
        'ca_file' => WWPASS_SPFE_CA_FILE
    ));
    $response = $wwc->getTicket(array(
        'ttl' => 300,
        'pin' => true
    ));

    $ttl = $response['ttl'];
    $ticket = $response['ticket'];
} catch (WWPass\Exception $e) {
    echo 'Caught WWPass exception: ' . $e->getMessage();
} catch (Exception $e) {
    echo 'Caught exception: ' . $e->getMessage();
}
```

## License

The WWPass PHP library is licensed under Apache 2.0 license
