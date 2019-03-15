FROM khutran/product:8

WORKDIR /var/www/workspace
ARG URLGIT
ARG BRANCH
#RUN crontab -l | { cat; echo "0 3 * * *  sh /backupdb.sh >/dev/null 2>&1"; } | crontab -

RUN apk add --no-cache git

RUN git clone $URLGIT .
RUN git checkout ${BRANCH}
RUN composer install
EXPOSE 443 80

CMD ["/start.sh"]
