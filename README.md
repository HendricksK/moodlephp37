# moodlephp37

docker setup to run moodle, doesPHP 7.3  with moodle 37 stable branch, uses mariadb 10, should use a bridge network, but this was built for windows, which does thatt automatically.

CLI into the apache docker container cd into /var/www/hml and run git clone https://github.com/moodle/moodle.git -b MOODLE_37_STABLE development

MYSQL_USER: 'user'
# You can use whatever password you like
MYSQL_PASSWORD: 'password'
# Password for root access
MYSQL_ROOT_PASSWORD: 'password'
