# sample-php-mysql-containerized-app

docker network create sample-php-mysql-containerized-network
cd mysql
docker build .
docker run --name mysql -d --network sample-php-mysql-containerized-network <image id>
cd ..
cd apache
docker build .
docker run --name apache -d --network sample-php-mysql-containerized-network -p 80:80 <image id>
