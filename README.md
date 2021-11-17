# sample-php-mysql-containerized-app

docker network create sample-php-mysql-containerized-network</br>
cd mysql</br>
docker build .</br>
docker run --name mysql -d --network sample-php-mysql-containerized-network <image id></br>
cd ..</br>
cd apache</br>
docker build .</br>
docker run --name apache -d --network sample-php-mysql-containerized-network -p 80:80 <image id></br>
