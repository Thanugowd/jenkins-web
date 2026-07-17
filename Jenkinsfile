pipeline {

    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Thanugowd/jenkins-web.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo cp target/*.war /opt/tomcat/webapps/'
            }
        }
    }

    post {

        success {
            echo 'Build and Deployment Successful'
        }

        failure {
            echo 'Pipeline Failed'
        }

    }

}
