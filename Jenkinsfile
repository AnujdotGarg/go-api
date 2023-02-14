pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                sh 'docker build -t anujgarg01/go-api:$BUILD_NUMBER .'
            }
        }
        stage('scan') {
            steps{
                sh 'trivy image anujgarg01/go-api:$BUILD_NUMBER'

            }
        }
            stage('stage docker push') {
            steps {
                sh 'docker login docker.io -u anujgarg01 -p Ekaansh@11'
                sh 'docker push anujgarg01/go-api:$BUILD_NUMBER'
            }
        }
    }
}