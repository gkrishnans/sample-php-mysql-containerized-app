node{
    stage('Clone repository') {
        checkout scm
    }

    stage ('build sql image') {
        sh "docker build -t mysql_image ./mysql"
    }

    stage ('build php image') {
        sh "docker build -t apache_image --no-cache ./apache"
    }

    stage ('create docker network') {
        sh "docker network create sample-php-mysql-containerized-network || true" 
    }

    stage ('run sql container') {      
      
        sh "(( docker stop mysql || true )) && docker run --name mysql -d -p 6033:3306 --network sample-php-mysql-containerized-network --rm mysql_image"
    }

    stage ('run php container') {
        sh "(( docker stop apache || true )) && docker run --name apache -d -p 80:80 --network sample-php-mysql-containerized-network --rm apache_image"
    }
}
