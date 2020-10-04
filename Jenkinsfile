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
                    docker build --no-cache -t demo .
                    
                    docker tag task_db2:latest 487920346599.dkr.ecr.us-east-1.amazonaws.com/task_db2:latest
                    
                    docker push 487920346599.dkr.ecr.us-east-1.amazonaws.com/task_db2:latest
                   
               '''
            }
        }


    }        
}
