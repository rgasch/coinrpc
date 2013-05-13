Coin RPC Client
===============

Coin RPC Client is a library to allow PHP to communicate with a live
bitcoind/litecoind etc RPC servers.

Getting started
---------------

### Installing via Composer

The recommended way to install CoinRpc is through [Composer](http://getcomposer.org).

1. Add ``drak/coinrpc`` as a dependency in your project's ``composer.json`` file:

        {
            "require": {
                "drak/coinrpc": "~1.0"
            }
        }

2. Download and install Composer:

        curl -s http://getcomposer.org/installer | php

3. Install your dependencies:

        php composer.phar install

4. Require Composer's autoloader

    Composer  prepares an autoloader file capable of autoloading all of the classes in
    any of the libraries that it downloads.Just add the following line to your code's bootstrap process:

        require 'vendor/autoload.php';

You can find out more on how to install Composer, configure autoloading, and other best-practices for defining
dependencies at [getcomposer.org](http://getcomposer.org).


Basic usage
-----------

```php
<?php

use CoinRpc\BitcoinClient;

$client = new Client('http://rpc_user:rpc_password@localhost:8332');

// optional SSL verification if required (off by default)
// $client->setSslVerification();

$info = $client->getInfo();
$balance = $client->getBalance();
$txid = $client->sendToAddress('138jklsdjklsjklfjklsdfklssdfs', (float) 0.1);
