pipeline {
    agent any

    stages {
        stage('taking source code from github') {
            steps {
                echo 'Hello World we are downloading github code'
                // using github option 
                git 'https://github.com/Umend10/umend-cisco-webUI.git'
                
                sh 'ls  '
                sh 'java -version'
            }
        }
        
        stage('building image and create container'){
            steps {
                echo 'Running docker command'
                sh 'docker version'
                sh 'docker-compose down'
                sh 'docker-compose up -d --build'
                sh 'docker images'
            }
        }
        
        stage('testing container status by accessing by page'){
            
            steps {
                sh 'curl -f http://localhost:1007/health.html'
                echo 'health page is working fine'
            }
        }
        
    }
}
