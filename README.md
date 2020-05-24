# LEMP Stack for Laravel

This is a basic lemp stack to run Laravel on a container. It is intended for development, and not production.

I'm learning docker at the moment, so if anyone sees anything that could be added or made better, please send a PR or open an issue!

## Usage

- Require this repo as a submodule on a project;
- See if any specific configuration should be added to `my.cnf`, `app.conf` and `local.ini` under the relevant directory of the `_docker` folder;
- Make sure the `.env` file of your Laravel project uses the required database values found down this readme;
- Run `docker-compose up -d` and have fun.

## Database config

Your `.env` file should be using these values for database. Modify yours accordingly if you changed anything in the `docker-compose` file.

```
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=secret
```

## Running artisan command

You can run any artisan command like so: `docker-compose exec app php artisan`. For example:

- Run migration: `docker-compose exec app php artisan migrate`
- Play in tinker: `docker-compose exec app php artisan tinker`