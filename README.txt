chown -R 1001:1001 var/lib
chown -R 1001:1001 etc/bitnami
mkdir -p etc/nginx/conf.d
mkdir -p var/workspace
mkdir -p etc/letsencrypt
mkdir -p var/backup
mkdir -p logs/nginx
mkdir -p var/lib/mysql
mkdir -p etc/bitnami/mysql/conf

- coppy .env.example .env
- thay thong tin vao .env
- clone code vào thư mục var/workspace
- login container cai dat web bang tay
- tao supervisord : var/workspace/.supervisord/*.ini
- tao cronjob : update docker/server/Dockerfile
