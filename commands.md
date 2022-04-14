chown nextcloud:nextcloud /etc/webapps/nextcloud/php.ini
export NEXTCLOUD_PHP_CONFIG=/etc/webapps/nextcloud/php.ini
install --owner=nextcloud --group=nextcloud --mode=700 -d /var/lib/nextcloud/sessions

mysql -u root -p
```
CREATE USER 'nextcloud'@'localhost' IDENTIFIED BY '<DATABASE_PASSWORD>';
CREATE DATABASE IF NOT EXISTS nextcloud CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
GRANT ALL PRIVILEGES on nextcloud.* to 'nextcloud'@'localhost';
FLUSH privileges;
``

occ maintenance:install \
    --database=mysql \
    --database-name=nextcloud \
    --database-host=localhost:/run/mysqld/mysqld.sock \
    --database-user=nextcloud \
    --database-pass=<DATABASE_PASSWORD> \
    --admin-pass=<ROOT_PASSWORD> \
    --admin-email=admin@edubase.lan \
    --data-dir=/var/lib/nextcloud/data
