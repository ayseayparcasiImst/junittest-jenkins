pipeline {
    agent any
    tools{
        maven "maven 3.5.0"
    }
    stages {
        stage('Build') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '3fd4127d-e3f3-423f-9490-e14fac1066d7', url: 'https://github.com/ayseayparcasiImst/junittest-jenkins.git']])
               sh 'mvn clean install'
                // bat '.\\mvnw clean compile'
            }
        }
        stage('Test') {
            steps {
                sh 'chmod +r pom.xml'
                sh 'chmod +r .mvn'
                sh './mvnw test'
                // bat '.\\mvnw test'
            }


        }
    }
}
