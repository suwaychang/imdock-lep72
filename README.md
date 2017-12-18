imdock-cnp7
====================================================

## What's this:

Centos(Nginx 1.12.2 + PHP7.2.0)

  * you can easy install PHP Framework (ex: symfony、Laravel)

  * this project use management by docker-compose

## How to install:

    ~ $ mkdir {project-name}
    ~ $ cd {project-name}
    ~/{project-name} $ git clone https://github.com/suwaychang/imdock-lep72.git
    ~/{project-name} $ cd imdock-lep72


#### change your custom settting (container_name: {project-name})

    ~/{project-name}/imdock-lep72 $ vim ./docker-compose-yml
    ~/{project-name}/imdock-lep72 $ docker-compose up

#### open browser, testing your host-ip, see the phpinfo is success! ctrl+c close this
#### now, you can move the your project to website dir

    ~/{project-name}/imdock-lep72 $ cp ./sites-enable/default.vhost.sample ./sites-enable/default.vhost

#### setting your custom nginx config (volumes: ./website:/var/www → ../{project-dir}:/var/www)

    ~/{project-name}/imdock-lep72 $ vim ./docker-compose-yml
    ~/{project-name}/imdock-lep72 $ vim ./default.vhost
    ~/{project-name}/imdock-lep72 $ docker-compose up -d


## Reference architecture:

```txt
{project-name}
├── imdock-lep72
│   ├── conf/
│   ├── sites-enable/(nginx website setting)
│   ├── sites-module/
│   ├── website(sample phpinfo)
│   ├── Dockerfile
│   └── docker-compose.yml
└── {project-dir}
    └── ...
```
## How to and other docker-compose use the same network :

    #if you not have group network, you can create this, and other docker-compose use this network setting
    ~ $ docker network create --driver bridge imdockgroup

## How to change setting:

  * You just look at this directory you will understand (lep72/config/*)

  * When the settings are complete, restart the container

## PHP Extend:

- [x] PHP7(7.2.0)
  - [x] mbstring
  - [x] mcrypt
  - [x] php-dom, php-domxml, php-wddx, php-xslxml, xmlrpc
  - [x] php-mysqli, php_database
  - [x] mongodb
  - [x] redis
  - [x] pgsql
  - [X] php-mssql
  - [x] pdo_sqlite, sqlite3
  - [x] apcu
  - [x] gd
  - [x] imap
  - [x] imagick
  - [x] zend-opcache
  - [ ] memcache
  - [ ] xdebug

