FROM mariadb:10.2

COPY my.cnf /etc/mysql/conf.d/my.cnf

# treat Windows
RUN chmod 644 /etc/mysql/conf.d/*

CMD ["mysqld"]

EXPOSE 3306
