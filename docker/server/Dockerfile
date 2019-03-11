FROM khutran/product:8

WORKDIR /var/www/workspace
#RUN crontab -l | { cat; echo "0 3 * * *  sh /backupdb.sh >/dev/null 2>&1"; } | crontab -
EXPOSE 443 80

CMD ["/start.sh"]
