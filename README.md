# VWA Lab for Classroom Training

|||
|---|---|
|![img](https://raw.githubusercontent.com/anir0y/cdn/0f5c11d25e25e1d5f1ffc749c9425346b3069b62/VWA%20(Circle%20Sticker).svg)|this lab is designed and developved by [@anir0y](https://twitter.com/anir0y) this is a way to teach students about common mistakes made by dev|


# setting up local web-application server

# 1 : setting up [LAMP stack](https://notes.anir0y.in/ubuntu-installing-lamp-stack)

LAMP stack is stands for: 

* Linux
* Apache (apache2)
* MySQL	(db)
* Php 	(scripting Lang.)

---

# 2 : download the web-application code.

you can download the code from this [GitHub Repo](https://github.com/anir0y/arishti-01)

# 3 : configuration

## MySql

```sql

# Login to MySQL

sudo mysql -u root 
# you'll be prompted by `mysql>` 

# create user with password

CREATE USER 'dbadmin'@localhost IDENTIFIED BY 'dbadmin@123';

# create db:

CREATE DATABASE users;

# select DB

use `users`;

# grant our user privileges

GRANT ALL PRIVILEGES ON users.* to 'dbadmin'@'localhost' ;

# creating tables:

CREATE TABLE IF NOT EXISTS `userlogin` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `username` varchar(200) NOT NULL,
  `password` varchar(33) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB  DEFAULT CHARSET=latin1 AUTO_INCREMENT=1 ;

# insert values:

INSERT INTO `userlogin` (`id`, `username`, `password`)VALUES (99, 'mentor', 'a1857b83457cfef98da22fefa2fdd3ba');
INSERT INTO `userlogin` (`id`, `username`, `password`)VALUES (1, 'admin', 'a1857b83457cfef98da22fefa2fdd3ba');
```

### PHP

* open `dbconf.php` add the creds:

```php

# old
new mysqli("127.0.0.1", "useradm", "useradm", "userdb");

# new
new mysqli("127.0.0.1", "dbadmin", "dbadmin@123", "users");
```


### Talk to me 
  - mail@anir0y.in
  - tweet: [@anir0y](https://twitter.com/anir0y)
  

