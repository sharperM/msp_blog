---
title: "worldpress 的sql数据库，导入数据"
date: 2023-03-06T20:11:04+08:00
draft: true
---



/var/www/goeasy.top/Goeasy22.top.sql


    mysql -uroot -p123456 < runoob.sql

```sql
create database mainDB;      # 创建数据库
use mainDB;                  # 使用已创建的数据库 
set names utf8;           # 设置编码
source /var/www/goeasy.top/Goeasy22.top.sql;
```



var/www/goeasy.top/wp-config.php
```php
/*?php
**
* WordPress基础配置文件。
*
* 这个文件被安装程序用于自动生成wp-config.php配置文件，
* 您可以不使用网站，您需要手动复制这个文件，
* 并重命名为“wp-config.php”，然后填入相关信息。
*
* 本文件包含以下配置选项：
 *
 * * MySQL设置
 * * 密钥
 * * 数据库表名前缀
 * * ABSPATH
 *
 * @link https://codex.wordpress.org/zh-cn:%E7%BC%96%E8%BE%91_wp-config.php
 *
 * @package WordPress
 */

// ** MySQL 设置 - 具体信息来自您正在使用的主机 ** //
/** WordPress数据库的名称 */
define('WP_CACHE', true);
define( 'WPCACHEHOME', '/var/www/goeasy.top/wp-content/plugins/wp-super-cache/' );
define('DB_NAME', 'mainDB');

/** MySQL数据库用户名 */
define('DB_USER', 'wpuser');

/** MySQL数据库密码 */
define('DB_PASSWORD', '123456');

/** MySQL主机 */
define('DB_HOST', 'localhost');

/** 创建数据表时默认的文字编码 */
define('DB_CHARSET', 'utf8');

/** 数据库整理类型。如不确定请勿更改 */
define('DB_COLLATE', '');
```


```sql
 CREATE USER 'wpuser'@'localhost' IDENTIFIED BY '123456';
 GRANT ALL PRIVILEGES ON *.* TO 'wpuser'@'localhost';
 FLUSH PRIVILEGES;
```

```
 service mysql restart
 service apache2 restart
```
