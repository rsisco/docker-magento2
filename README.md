# Docker Magento 2 Development Environment


### Intro
This development environment has been in testing for the last four months. It was developed by me after digging through Inchoo's blog (https://inchoo.net/magento-2/development-environment-magento-2-using-docker/)

After consulting Clean Docker (https://github.com/clean-docker/Magento2)

After consulting ManBee Docker (https://github.com/meanbee/docker-magento2)

And after looking over several other Docker environments. I took small pieces from each one until I could get a stable, repeated install on a variety of enviornments.

The use case for these was in a wide multi-client environment where it was common to have very unusual clients and needed large swaths of variables from MariaDB to Mysql 5.6, 5.7 or Percona. 

This is the most stable build.

I do not take any credit for the bin/ commands I took those from Mark Shust
 (https://github.com/markoshust/docker-magento/tree/master/compose/magento-2/bin)

They are short and sweet and it seemed silly to rewrite something already written by another developer.

### Setup Instructions
1. Clone this repo into a folder named for the site in our case magento2.local
2. If using an existing site, clone the repo into the src/ folder
3. Run bin/setup (after first run use bin/start)
4. Copy the Database Dump into src/
5. Add the site to the /etc/hosts file at 127.0.0.1 
    * echo "127.0.0.1 magento2.local" | sudo tee -a /etc/hosts
6. Run bin/bash
7. Run composer install
8. Import the database
9. Run bin/magento cache:clean && bin/magento cache:flush
10. Exit Docker
11. open https://magento2.local (other other domain)

### New Install Instructions
1. Clone this repo into a folder named for the site in our case magento2.local
2. Run ./bin/download Major.Minor.Increment (2.2.7 or 2.3.0)
3. Run ./bin/setup
4. Copy the Database Dump into src/
5. Add the site to the /etc/hosts file at 127.0.0.1
    * echo "127.0.0.1 magento2.local" | sudo tee -a /etc/hosts
6. Run bin/bash
7. Run composer install
8. Import the database
9. Run bin/magento cache:clean && bin/magento cache:flush
10. Exit Docker
11. open https://magento2.local (other other domain)
