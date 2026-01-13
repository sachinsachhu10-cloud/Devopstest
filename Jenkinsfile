pipeline {
    agent any

    stages {
        stage('Git Clone') {
            steps {
                git 'https://github.com/sachinsachhu10-cloud/Devopstest.git/java-cicd'
            }
        }

        stage('Maven Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t java-cicd-app .'
            }
        }

        stage('Kubernetes Deploy') {
            steps {
                sh '''
                kubectl apply -f deployment.yaml
                kubectl apply -f service.yaml
                '''
            }
        }
    }
}

