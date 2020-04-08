# Belugapay library to connect to the ecommerce api

## Run project

### Requeriments

* Docker installed

### Installation

Clone repository

``` sh
git clone https://github.com/belugapaydevs/ecommerce-php
```

## Transactions

Import the main file

``` php
require_once dirname(__FILE__).'/lib/Belugapay-ecommerce/BelugaPay.php';
```

Add the api key that you want to use

``` php
use \BelugaPay\User;
User::setApiKey(YOUR APIKEY);
```

Create an instance of the Sale class

``` php
use \BelugaPay\Sales;
$sale = new Sales();
```

Add information to transaction

``` php
$cardHolder = array(
  'cardHolder' => array (
    'name' => '',
    'email' => '',
    'phone' => '+52...'
  )
);
$card = array(
  'card' => array (
    'card' => '',
    'expires' => '',
    'cvv' => '',
  )
);
$address = array(
  'address' => array (
    'country' => 'MX',
    'state' => '',
    'city' => '',
    'numberExt' => '',
    'numberInt' => '',
    'zipCode' => '',
    'street' => '',
  )
);
$transaction = array(
  'saleTransaction' => array (
    'amount' => ''
  )
);
```

Make transaction

``` php
$sale->sale($cardHolder, $card, $address, $transaction);
```

Json response

``` json
{
  "codigo": 200,
  "mensaje": "Aprobada",
  "data": {
    "transaction": {
      "transactionId": "917",
      "authCode": "492507",
      "cardType": null,
      "autStatusResult": "A",
      "autResult": null,
      "cardBrand": null,
      "reference": "975471683465",
      "controlNumber": "LIPC77d071018363405aaa1a50bd20",
      "issuingBank": null,
      "custReqDate": "2020-01-05 18:11:11",
      "custRespDate": "2020-01-05 18:11:11",
      "autReqDate": null,
      "autRespDate": null,
      "pan": "4536"
    }
  }
}
```

## Authors

* MSlinky
