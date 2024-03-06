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
                build 'PES1UG21CS647-1'
            }
        }
        
        stage('Test') {
            steps {
                sh './output'
                 script {
                    def output = sh(script: './output', returnStdout: true).trim()
                    echo "Output of main.cpp: ${output}"
                }
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
