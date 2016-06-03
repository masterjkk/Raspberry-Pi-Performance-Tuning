# Raspberry-Pi-Performance-Tuning 
Maximum your Raspberry Pi's performance, especially when you are anxiety about your owncloud performance with Nginx+Mysql+PHP structure


After serveral days digging the solution of bad performance with owncloud in lnmp, I will tell you how to optimize your Rasperry pi along with my story.<br>
1. Try the latest version of Nginx and PHP, I use Nginx 1.10.1 with http/2 and PHP 7.0.7 for the time being;<br>
2. You SHOULDN'T use InnoDB! To use MyISAM instead!<br>
3. Compile PHP-redis, and use owncloud with it;<br>
4. Compile as less modules as possible, taking PHP as an example:<br>
   ./configure --prefix=/usr/local/php7 --with-config-file-path=/usr/local/php7/etc --with-config-file-scan-dir=/usr/local/php7/etc/conf7.d --enable-mysqlnd --with-mysqli --with-pdo-mysql --enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data --enable-xml --with-gd --with-iconv --enable-mbstring --enable-zip --with-zlib --with-curl=/usr/local/curl --enable-intl --with-openssl=/usr/local/openssl --enable-exif --enable-opcache --enable-sockets --enable-mbregex --with-bz2=/usr/local/bzip2 --enable-calendar --disable-ipv6 --without-sqlite3 --without-pdo-sqlite<br>
5. Use an Class 10 SD card to drive your Pi, you will never regret it;<br>
6. Use a USB hub for connecting external USB Disks, from my experience, using a hub will provide a up to 3MB/S speed increase;<br>
7. http/2 helps little when you and your Pi are in the same LAN;<br>
8. Include OPCACHE in your php7 immediately you finished installing;<br>
9. This works for Raspberry Pi 3, maybe the same to Pi 2. <br>
