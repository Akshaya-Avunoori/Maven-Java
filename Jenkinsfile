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



Step	Command	Purpose
1	docker --version	Check Docker installation
2	docker pull redis	Download Redis image
3	docker run --name my-redis -d redis	Create and start container
4	docker ps	Display running containers
5	docker exec -it my-redis redis-cli	Enter Redis CLI
6	SET name "Alice"	Store data (inside Redis CLI)
7	GET name	Retrieve data (inside Redis CLI)
8	exit	Exit Redis CLI
9	docker stop my-redis	Stop container
10	docker start my-redis	Start container again
11	docker stop my-redis	Stop container
12	docker rm my-redis	Remove container
docker rmi redis

Practical 2: Create a Custom Docker Image
Open PowerShell.
1	mkdir redis-docker	Create folder
2	cd redis-docker	Enter folder
3	notepad Dockerfile	Open Notepad to create Dockerfile

Inside Notepad, type:
FROM redis:latest
CMD ["redis-server"]

4. Click File → Save and save it as Dockerfile (without .txt). Close Notepad.

Continue in PowerShell:
Step	Command	Purpose
4	docker build -t redisnew .	Build custom image
5	docker images	View images
6	docker run --name myredisnew -d redisnew	Run container
7	docker ps	Check container
8	docker exec -it myredisnew redis-cli	Enter Redis CLI
9	SET name "Akshaya"	Store data
10	GET name	Retrieve data
11	exit	Exit Redis CLI
12	docker stop myredisnew	Stop container
13	docker rm myredisnew	Remove container
14	docker rmi redisnew	Remove custom image

Practical 3: Docker Hub – Commit, Push and Pull
Open PowerShell.
Step	Command	Purpose
1	docker login	Login to Docker Hub
2	docker pull redis	Download Redis image
3	docker run --name my-redis -d redis	Create container
4	docker commit my-redis akshayaavunoori/redis1	Create image from container
5	docker images	Check image
6	docker push akshayaavunoori/redis1	Upload image to Docker Hub
7	docker stop my-redis	Stop container
8	docker rm my-redis	Remove container
9	docker rmi akshayaavunoori/redis1	Remove local image
10	docker logout	Logout
11	docker pull akshayaavunoori/redis1	Download image from Docker Hub
12	docker run --name myredis -d akshayaavunoori/redis1	Run downloaded image
13	docker exec -it myredis redis-cli	Enter Redis CLI
14	SET name "Abcdef"	Store data
15	GET name	Retrieve data
16	exit	Exit Redis CLI
17	docker stop myredis	Stop container
18	docker rm myredis	Remove container







