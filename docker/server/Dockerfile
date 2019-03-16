FROM khutran/product:8

WORKDIR /var/www/workspace
ARG URLGIT
ARG BRANCH
ARG MYSQL_USER
ARG MYSQL_PASSWORD
ARG MYSQL_DATABASE
#RUN crontab -l | { cat; echo "0 3 * * *  sh /backupdb.sh >/dev/null 2>&1"; } | crontab -

RUN apk add --no-cache git

RUN git clone ${URLGIT} .
RUN git checkout ${BRANCH} 

RUN cp .env.example .env
RUN sed -i \
    -e "s/DB_DATABASE=vicoders_vinaco/DB_DATABASE=${MYSQL_DATABASE}/g" \
    -e "s/DB_USERNAME=homestead/DB_USERNAME=${MYSQL_USER}/g" \
    -e "s/DB_PASSWORD=secret/DB_PASSWORD=${MYSQL_PASSWORD}/g" \
    .env

RUN composer install 
RUN php artisan migrate --seed

EXPOSE 443 80

CMD ["/start.sh"]