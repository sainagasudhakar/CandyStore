pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: '']]) 
            }
        }
        stage('docker') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'sssss') {
                         sh 'docker build -t sainagasudhakar/supercandy .'
                         sh 'docker push sainagasudhakar/supercandy:latest'
                   }
               }
            }
        }
    }
}
