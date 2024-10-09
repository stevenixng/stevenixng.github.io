---
title: user admin
---

#### set root password
    UPDATE mysql.user SET password = PASSWORD('newpassword') WHERE user = 'root';

#### disable auth plugin
    sudo mysql -u root
    [mysql] use mysql;
    [mysql] update user set plugin='' where User='root';
    [mysql] flush privileges;
    [mysql] \q
