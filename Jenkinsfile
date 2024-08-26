pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                sh 'https://github.com/Praveenchinna14/CandyStore.git'
            }
        }
        stage('docker') {
            steps {
                script {
                     withDockerRegistry(credentialsId: 'docker-cred') {
                         sh 'docker build -t praveenchinna/candystore .'
                         sh 'docker push praveenchinna/candy:latest'
                   }
               }
            }
        }
    }
}
