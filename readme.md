# Docker network for local development

Clone this repo to setup local environment for Laravel and WordPress development.

## Requirements
- Composer version 2+
- wget
## Installation

``` bash
$ git clone https://github.com/cssjockey/docker-local-dev.git
```

## Usage
Run the command below to install and setup a Laravel or WordPress app.
```
$ ./bash/laravel
```
```
$ ./bash/wordpress
```
Both commands will ask for `directory name` and install the app under `./apps` folder and initialize a blank repository for the same.

Once installed, you will see the network IP addresses and PORT numbers which you can use to connect to postgres, mysql and redis database.

## Environment Variables
Following enviornment variables are available in the `.env` file and you are free to change these as per your requirements.

```
NETWORK_NAME=localdev

REDIS_PORT=7000
POSTGRES_PORT=7001
POSTGRES_TEST_PORT=7002
MYSQL_PORT=7003
MYSQL_TEST_PORT=7004

REDIS_CONTAINER_NAME=local-redis
POSTGRES_CONTAINER_NAME=local-postgres
POSTGRES_TEST_CONTAINER_NAME=local-postgres_test
MYSQL_CONTAINER_NAME=local-mysql
MYSQL_TEST_CONTAINER_NAME=local-mysql_test


POSTGRES_DB=local_app
POSTGRES_TEST_DB=app_test
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password

MYSQL_DB=local_app
MYSQL_TEST_DB=app_test
MYSQL_USER=root
MYSQL_PASSWORD=password
```

__IMPORTANT:__ If you decide to change the `NETWORK_NAME` then you must change all occurances of `localdev` string in following directories:

*For new apps:*
```
./bash/docker/laravel
./bash/docker/wordpress
```
*For existing apps:*
```
./apps/{app-1-dir}/docker
./apps/{app-2-dir}/docker
./apps/{app-3-dir}/docker
./apps/...
```



## Available root level commands

```
$ ./bash/run
```
This will create the docker network and start all service containers.

```
$ ./bash/stop
```
This will stop all network service containers.

```
$ ./bash/clean
```
This will remove all custom networks, unused images and containers. User this command only if you wish to clean up your system of Docker junk.

```
$ ./bash/ip
```
This will display the IP addresses of containers in the network. You can use these IP addresses to in your **.env** files such as `DB_HOST`.

```
$ ./bash/list
```
This will display the containers information such as local and internal ports in the network. You can use the external ports to connect to databases via GUI client such as TablePlus or MySQL Workbench and use internal ports in your **.env** files such as `DB_PORT`.

## Laravel App Commands

```
$ ./docker/run
```
This command will ask for the `PORT` number and run the app. You can access the app in browser with either `http://localhost:{PORT}` or `http://0.0.0.0:{PORT}`
```
$ ./docker/stop
```
This command will stop the app container.
```
$ ./docker/restart
```
This command will stop the app and then ask for `PORT` number to start the app again.
```
$ ./docker/artisan <command>
```
This command will run the artisan commands in the container. 
e.g. 
`./docker/artisan cache:clear` will clear the cache.
`./docker/artisan migrate --seed` will migrate and seed the database.
```
$ ./docker/composer <command>
```
This command will run the composer commands in the container. 
e.g. 
`./docker/composer require package-name` will install the composer package.
`./docker/composer install` will install the composer dependencies.
`./docker/composer update` will update the composer dependencies.
```
$ ./docker/phpunit <args>
```
This command will run phpunit tests in the container.
 e.g. 
`./docker/phpunit --filter Example` will run all tests filtered by Example.
```
$ ./docker/bash
```
You can run this command to ssh into the container.

## Wordpress App Commands

```
$ ./docker/run
```
This command will ask for the `PORT` number and run the app. You can access the app in browser with either `http://localhost:{PORT}` or `http://0.0.0.0:{PORT}`
```
$ ./docker/stop
```
This command will stop the app container.
```
$ ./docker/restart
```
This command will stop the app and then ask for `PORT` number to start the app again.
```
$ ./docker/bash
```
You can run this command to ssh into the container.

## Change log

Please see [change log](changelog.md) for details and a todolist.
## Contributing

Please see [contributing](contributing.md) for details and a todolist.

## Security

If you discover any security related issues, please email admin@cssjockey.com instead of using the issue tracker.

## Credits

- [Mohit Aneja][link-author]
- [All Contributors][link-contributors]

## License

GNU GPLv3. 
Please see the [license file](license.md) for more information.

