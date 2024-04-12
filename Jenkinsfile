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
    }
}