# Redis PSR-6 Cache pool
[![Gitter](https://badges.gitter.im/php-cache/cache.svg)](https://gitter.im/php-cache/cache?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
[![Latest Stable Version](https://poser.pugx.org/cache/redis-adapter/v/stable)](https://packagist.org/packages/cache/redis-adapter)
[![codecov.io](https://codecov.io/github/php-cache/redis-adapter/coverage.svg?branch=master)](https://codecov.io/github/php-cache/redis-adapter?branch=master)
[![Total Downloads](https://poser.pugx.org/cache/redis-adapter/downloads)](https://packagist.org/packages/cache/redis-adapter)
[![Monthly Downloads](https://poser.pugx.org/cache/redis-adapter/d/monthly.png)](https://packagist.org/packages/cache/redis-adapter)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)

This is a PSR-6 cache implementation using Redis. It is a part of the PHP Cache organisation. To read about
features like tagging and hierarchy support please read the shared documentation at [www.php-cache.com](https://www.php-cache.com).

This implementation is using [PhpRedis](https://github.com/phpredis/phpredis). If you want an adapter with
[Predis](https://github.com/nrk/predis) you should look at our [Predis adapter](https://github.com/php-cache/predis-adapter).

### Install

```bash
composer require cache/redis-adapter
```

### Use

To create an instance of `RedisCachePool` you need to configure a `\Redis`, `\RedisArray` or `\RedisCluster` client.

\Redis
```php
use Cache\Adapter\Redis\RedisCachePool;

$client = new \Redis();
$client->connect('127.0.0.1', 6379);
$pool = new RedisCachePool($client);
```

\RedisArray
```php
$client = new \RedisArray(['127.0.0.1:6379', '127.0.0.2:6379']);
$pool = new RedisCachePool($client);
```

\RedisCluster
```php
$client = new \RedisCluster(null, ['127.0.0.1:7000', '127.0.0.2:7001', '127.0.0.2:7002',]);
$pool = new RedisCachePool($client);
```

_See [PhpRedis](https://github.com/phpredis/phpredis) for more connection options_

### Contribute

Contributions are very welcome! Send a pull request to the [main repository](https://github.com/php-cache/cache) or
report any issues you find on the [issue tracker](http://issues.php-cache.com).
