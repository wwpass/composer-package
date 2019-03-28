# WWPass API for multifactor authentication and data access

Composer-compliant WWPass API client library.

For single-file non-composer library please refer to [https://github.com/wwpass/wwpass-php-sdk](https://github.com/wwpass/wwpass-php-sdk).

## Installation

```bash
$ composer require wwpass/apiclient:dev-master
```

## Usage

The library defines two classes in the WWPass namespace: **WWPass\Connection** and **WWPass\Exception**.

```php
require_once 'vendor/autoload.php';

try {
    $wwc = new WWPass\Connection(WWPASS_KEY_FILE, WWPASS_CERT_FILE, WWPASS_CA_FILE);
    $ticket = $wwc->getTicket(WWPASS_TICKET_TTL, WWPASS_PIN_REQUIRED?'p':'');
} catch (WWPASS\Exception $e) {
    echo 'Caught WWPass exception: ' . $e->getMessage();
} catch (Exception $e) {
    echo 'Caught exception: ' . $e->getMessage();
}
```

## License

The WWPass PHP library is licensed under Apache 2.0 license
