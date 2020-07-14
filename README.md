Docker Compose Magento
====
Docker Compose environment with Magento 2.3.5 preinstalled under `_magento`. 
Alternatively, install your own copy of Magento under `_magento`. 
Maybe one day move Magento install/setup to composer based. Maybe add redis, elasticsearch, varnish, etc.

Usage
-----

1. bring your instance up: \
```$ docker-compose up -d```

1. install php dependencies: \
```$ docker exec -it magento-app /bin/bash``` \
```$ composer install```

1. Visit: http://localhost/

1. take your instance down: \
```$ docker-compose down```

Considerations
----
1. Magento
