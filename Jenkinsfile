pipeline {
    agent any
    
 
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/Arif-git/task_db2.git'
            }
        }


        
        stage('Docker-Build & Push-to-ECR') {
            steps {
                sh '''
                    whoami
                    aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 487920346599.dkr.ecr.us-east-1.amazonaws.com
                    docker build -t task_db2 .
                    
                    docker tag task_db2:latest 487920346599.dkr.ecr.us-east-1.amazonaws.com/task_db2:latest
                    
                    docker push 487920346599.dkr.ecr.us-east-1.amazonaws.com/task_db2:latest
                   
               '''
            }
        }


    }        
}
