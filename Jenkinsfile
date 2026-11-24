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
