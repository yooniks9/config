### wordpress

```
UPDATE wp_options SET option_value = replace(option_value, 'http://www.oldurl', 'http://www.newurl');
UPDATE wp_posts SET guid = replace(guid, 'http://www.oldurl','http://www.newurl');
UPDATE wp_posts SET post_content = replace(post_content, 'http://www.oldurl', 'http://www.newurl');
UPDATE wp_postmeta SET meta_value = replace(meta_value,'http://www.oldurl','http://www.newurl');
```

### create DB

```
CREATE DATABASE mydb DEFAULT CHARACTER SET utf8mb4 DEFAULT COLLATE utf8mb4_unicode_ci;
```

### Grant

```
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'PasZw02D';
```

### MySQL 5.7 no root password fix

```
sudo systemctl stop mysql

sudo mkdir /var/run/mysqld; sudo chown mysql /var/run/mysqld

sudo mysqld_safe --skip-grant-tables&

sudo mysql --user=root mysql

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'my_new_pass';

FLUSH PRIVILEGES;
```

