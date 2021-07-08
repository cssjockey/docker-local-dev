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

## Change log

Please see [change log](changelog.md) for details and a todolist.

## Testing

wip

## Contributing

Please see [contributing](contributing.md) for details and a todolist.

## Security

If you discover any security related issues, please email admin@cssjockey.com instead of using the issue tracker.

## Credits

- [Mohit Aneja][link-author]
- [All Contributors][link-contributors]

## License

MIT. Please see the [license file](license.md) for more information.
