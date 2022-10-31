pipeline {
    agent any
    environment {
        acrregistry = "hellocloudcontainerregistry.azurecr.io"
        acrCredentials= "tsing"
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/tbsingh/hellocloud']]])
            }
        }
        stage('Build Image') {
            steps {
                script {
                    dockerImage = docker.build acrregistry ":$BUILD_NUMBER"
                }
            }
        }
        // stage('Build Image') {
        //     steps {
        //         script {

        //         }
        //     }
        // }
    }
}
