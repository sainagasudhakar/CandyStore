pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/anilmaripi/CandyStore.git']]) 
            }
        }
        stage('docker') {
            steps {
                script {
                 withDockerRegistry(credentialsId: 'javaID') {
                         sh 'docker build -t anilmaripi/supercandy .'
                         sh 'docker push anilmaripi/supercandy:latest'
                   }
               }
            }
        }
    }
}
