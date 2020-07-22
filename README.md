# moodlephp37

docker setup to run moodle, doesPHP 7.3  with moodle 37 stable branch, uses mariadb 10, should use a bridge network, but this was built for windows, which does that automatically.

if you are running macos, you can add this to your docker compose file at the db service

container_name: 'db-mysql-dev'
    networks:
      default:
        ipv4_address: 172.20.0.3
        
this will bind the DB service to a specified IP, so you can access it at 172.20.0.3 instead of localhost. 

if you run into any bind issues, you can also set different ports see https://github.com/kurvinh/docker-compose-lamp/blob/master/docker-compose.yml as an example

CLI into the apache docker container cd into /var/www/hml and run git clone https://github.com/moodle/moodle.git -b MOODLE_37_STABLE development

MYSQL_USER: 'user'
# You can use whatever password you like
MYSQL_PASSWORD: 'password'
# Password for root access
MYSQL_ROOT_PASSWORD: 'password'
