FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1 \
    MYSQL_USER=expense \
    MYSQL_PASSWORD=ExpenseApp@1 \
    MYSQL_DATABSE=transactions
#When container is started for the first time all the files found in /docker-entrypoint-initdb.d/ will be executed  
COPY scripts/*.sql /docker-entrypoint-initdb.d/
