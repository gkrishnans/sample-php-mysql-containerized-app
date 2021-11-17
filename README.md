# sample-php-mysql-containerized-app
git clone https://github.com/gkrishnans/sample-php-mysql-containerized-app.git</br>
docker network create sample-php-mysql-containerized-network</br>
cd mysql</br>
docker build .</br>
docker run --name mysql -d --network sample-php-mysql-containerized-network --rm _image id_</br>
cd ..</br>
cd apache</br>
docker build .</br>
docker run --name apache -d --network sample-php-mysql-containerized-network -p 80:80 --rm _image id_</br>
