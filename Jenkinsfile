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



