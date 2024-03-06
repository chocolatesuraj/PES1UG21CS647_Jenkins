pipeline {
    agent any
    
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/chocolatesuraj/PES1UG21CS647_Jenkins.git']]])
            }
        }
        
        stage('Build') {
            steps {
                sh 'g++ main.cpp -o output'
            }
        }
        
        stage('Test') {
            steps {
                sh './output'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploy'
                //sh 'non_existent_command_failiure'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
