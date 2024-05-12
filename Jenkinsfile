pipeline {
    agent any
    stages {
        stage('discovery') {
            steps {
                echo 'discovery'
            }
        }
        stage('build discovery') { 
            steps {
                sh 'mvn clean install'
            }
        }

        stage('build image discovery') {
            steps {
                script {
                    account = docker.build("fernandowi55/discovery:${env.BUILD_ID}", "-f Dockerfile .")
                }
            }
        }

        stage('push image discovery') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-credential') {
                        account.push("latest")
                        account.push("${env.BUILD_ID}")
                       
                    }
                }
            }
        }
              
    }
}