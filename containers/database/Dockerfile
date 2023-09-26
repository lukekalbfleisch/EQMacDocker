FROM mariadb:10.5

ADD Server/loginserver/login_util/tblloginserversettings.sql /docker-entrypoint-initdb.d
ADD Server/utils/sql/database_full/quarm_2023-09-18-21_05.tar.gz /docker-entrypoint-initdb.d
ADD Server/utils/sql/git/required/2023_08_1*.sql /docker-entrypoint-initdb.d
ADD Server/utils/sql/git/required/2023_08_2*.sql /docker-entrypoint-initdb.d
ADD Server/utils/sql/git/required/2023_08_3*.sql /docker-entrypoint-initdb.d
ADD Server/utils/sql/git/required/2023_09*.sql /docker-entrypoint-initdb.d
ADD containers/database/launcher_boats.sql /docker-entrypoint-initdb.d/z_launcher_boats.sql

RUN rm /docker-entrypoint-initdb.d/drop_system.sql && \
    mv /docker-entrypoint-initdb.d/quarm_2023-09-18-21:05.sql /docker-entrypoint-initdb.d/0000-quarm_2023-09-18-21:05.sql && \
    mv /docker-entrypoint-initdb.d/player_tables_2023-09-18-21:05.sql /docker-entrypoint-initdb.d/0001-player_tables_2023-09-18-21:05.sql && \
    mv /docker-entrypoint-initdb.d/login_tables_2023-09-18-21:05.sql /docker-entrypoint-initdb.d/0002-login_tables_2023-09-18-21:05.sql && \
    mv /docker-entrypoint-initdb.d/data_tables_2023-09-18-21:05.sql /docker-entrypoint-initdb.d/0003-data_tables_2023-09-18-21:05.sql
