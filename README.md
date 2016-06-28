# WPDockerCompose
Docker-Compose for php / nginx / mysql to use with WordPress

```php
docker-compose build
docker-compose up
```

#### Download latest version of WordPress and unzip into

```php
/sites/www/
```

#### update your /etc/hosts

```php
<ip address from docker-machine env> dev.wp.local
```

#### visit to isntall wordpress

http://dev.wp.local/index.php

#### WP install screen

```
db name: wordpressdb
db user: admin
db pass: password
database connection: NOT localhost, enter "mysql"
```