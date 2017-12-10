# yii_docker_env

for installation:
1. install docker version >= 17.09.0-ce from https://docs.docker.com/engine/installation/ .
2. install docker-compose version >= 1.16.1 from https://docs.docker.com/compose/install/ .

3. locate the code at php_code/yii2advances/advanced, the code from https://github.com/ozarvatz/yii2advances.git.
4. cd to env folder.
5. docker-compose -f docker-compose-yii2-advanced.yml up -d
6. http://localhost:8000/frontend.dev/index.php?r=game

the docker-compose will create:
php 5.6 and apache machine with composer.
mysql 5.5.
phpmyadmin - localhost:8181 username : root password : 1234 .

to get into command line:
docker ps -a
copy the container_id of env_yii2_advanced
docker exec -it container_id bash




