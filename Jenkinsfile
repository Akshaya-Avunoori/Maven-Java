pipeline {
    agent any

    tools {
        maven 'Maven-3.9.16'
    }

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Run') {
            steps {
                bat 'java -jar target/Maven-Java-0.0.1-SNAPSHOT.jar'
            }
        }
    }
}




//Script 

pipeline {
    agent any

    stages {
        stage('Hello 1') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Hello3') {
            steps {
                echo 'Hello 3'
            }
        }
    }
}



//Script big

pipeline {
    agent any
    tools{
        maven 'MAVEN-HOME'
    }
    stages {
        stage('git repo & clean') {
            steps {
                //bat "rmdir  /s /q mavenjava"
                bat "git clone provide your github link"
                bat "mvn clean -f mavenjava"
            }
        }
        stage('install') {
            steps {
                bat "mvn install -f mavenjava" #project name#
            }
        }
        stage('test') {
            steps {
                bat "mvn test -f mavenjava"
            }
            
        }
        stage('package') {
            steps {
                bat "mvn package -f mavenjava"
            }
        }
    }
}



//DockerFile - For Maven Java
FROM eclipse-temurin:21-jre

WORKDIR /app

COPY target/Maven-Java-0.0.1-SNAPSHOT.jar app.jar

CMD ["java", "-jar", "app.jar"]


//DockerFile - For Maven Web



FROM tomcat:9.0-jdk17-temurin

RUN rm -rf /usr/local/tomcat/webapps/*

COPY target/Maven-Web-App.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

CMD ["catalina.sh", "run"]


---AWS---
sudo apt update
sudo apt-get install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
sudo apt install git -y
sudo apt install nano -y
git clone https://github.com/Akshaya-Avunoori/maven-web-project.git
cd maven-web-project
ls
ls target
cat Dockerfile

FROM tomcat:9.0-jdk21-temurin

RUN rm -rf /usr/local/tomcat/webapps/*

COPY target/maven-web-project.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

CMD ["catalina.sh", "run"]

sudo docker build -t maven-web-app .
sudo docker run -d --name app-demo -p 6060:8080 maven-web-app
sudo docker ps

http://YOUR-PUBLIC-IP:6060


Kubernetis:

minikube version
minikube kubectl -- version
java -version
mvn -version

Open CMD as Administrator
minikube status
minikube start --driver=docker
minikube kubectl -- get nodes
minikube kubectl -- get pods
minikube kubectl -- get deployments
minikube kubectl -- get services
minikube kubectl -- create deployment mynginx --image=nginx
minikube kubectl -- get deployments
minikube kubectl -- scale deployment mynginx --replicas=4
minikube kubectl -- get pods
minikube kubectl -- expose deployment mynginx --type=NodePort --port=80
minikube kubectl -- get services
minikube service mynginx

Open another CMD window and run:
minikube dashboard
Open another CMD window.
docker ps -a
docker start nagiosdemo
docker pull jasonrivers/nagios:latest
docker run --name nagiosdemo -p 8888:80 jasonrivers/nagios:latest

http://localhost:8888

Username	nagiosadmin
Password	nagios

docker ps







