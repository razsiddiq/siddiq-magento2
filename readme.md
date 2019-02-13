
/*Siddiq Magento-2 Docker*/

/*

Worked UBUNTU 18.04 

PHP7.3.0

*/



Download From WeTransfer since file is too large.


https://wetransfer.com/downloads/59ed2b4e0cde233876e3ca23b22df3fa20190213130830/dc784847b2c6d764a0e6e866f861231220190213130830/d95487


Extract File to wishing folder

cd /Demo

Inside the Project folder

Choose a domain name you would like to use to access the site and add it to your hosts file.

sudo -- sh -c "echo '127.0.0.1 local.domain.com' >> /etc/hosts"


Use this comment then

docker-compose up -d --build

In a web browser, go to 127.0.0.1:8080 and make sure that you can see phpMyAdmin. If you can, it was a success.


Access your Docker web container's command line.

docker exec -it web bash


Navigate to the web document root.

cd /app

Optional but recommended: deploy sample data.

php bin/magento sampledata:deploy



you must replace the values on lines 2-6 with your own details. On lines 7-8, replace the placeholder domain

php bin/magento setup:install \
--admin-firstname=siddiq \
--admin-lastname=khan \
--admin-email=siddiq.jalalu@gmail.com \
--admin-user=admin \
--admin-password='SomePassword123' \
--base-url=https://local.domain.com \
--base-url-secure=https://local.domain.com \
--backend-frontname=admin \
--db-host=mysql \
--db-name=magento \
--db-user=root \
--db-password=root \
--use-rewrites=1 \
--language=en_US \
--currency=USD \
--timezone=America/New_York \
--use-secure-admin=1 \
--admin-use-security-key=1 \
--session-save=files \
--use-sample-data



Docker Commands

    Spin Up

    docker-compose up -d --build

    Tear Down

    docker-compose down

    Connect to web container CLI

    docker exec -it web bash

    Connect to database container CLI

    docker exec -it mysql bash




