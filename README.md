# Laravel sandbox

## Via Vagrant

Create and edit `./provisioning/group_vars/all`

```
db_name: laravel
db_user: laravel
db_password: password
app_path: /vagrant/web
```

Start development server

```
vagrant up
```

<http://192.168.33.10:8080/>

## Via Docker

Install dependencies

```
docker run --rm -it -v `pwd`/web:/opt/project -w /opt/project composer composer i
docker run --rm -it -v `pwd`/web:/opt/project -w /opt/project node:12.18.4-slim npm i
```

Create and edit env files

```
cp docker/.env.example docker/.env
cp web/.env.example web/.env
```

Generate application key

```
docker run --rm -it -v `pwd`/web:/opt/project -w /opt/project php:7.4-cli php artisan key:generate
```

Start development server

```
docker-compose up -d
```

<http://localhost:8080/>
