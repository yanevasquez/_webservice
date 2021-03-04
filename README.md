### webservices

##### 1. Configure parameters in .env
```
cp .env.example .env
```

```
DB_CONNECTION=pgsql
DB_HOST=db
DB_PORT=5432
DB_DATABASE=postgres
DB_USERNAME=postgres
DB_PASSWORD=postgres
PGUSER=postgres
```
##### 2. Run the script to build a container 

```sh
cd src/
sh build.sh
```
##### 3. Api running at
```sh
http://localhost:3000
```

**Run migrations**
```sh
docker-compose exec api php artisan migrate
```
##### Useful commands:

Stop apache server to avoid conflict with nginx: 
```sh
sudo systemctl stop apache2
```
Clear cache after modifying .env: 
```sh
php artisan config:clear
php artisan view:clear
php artisan cache:clear
```
Access permission:
```sh
sudo chmod 777 -R storage/
```
Running application seed:
```
docker-compose exec api php artisan db:seed
```
Running migrate and seeders:
```
docker-compose exec api php artisan migrate:refresh --seed