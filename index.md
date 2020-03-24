## 手动单机部署
```shell script
git clone git@github.com:jeffid/laravel-shop.git
cd laravl-shop && git checkout dev6
cp .env.example .env
# 安装扩展
composer install
yarn install
yarn prodction

php artisan key:generate
# 迁移数据如果是docker环境,那要在项目的运行环境中执行,如docker中的workspace
php artisan migrate
php artisan db:seed
php artisan db:seed --class=DDRProductsSeeder
php artisan es:migrate
php artisan es:sync-products
# 导入后台数据 database/admin.sql
```
