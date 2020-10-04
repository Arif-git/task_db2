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
                    docker build --no-cache -t Demo .
                    docker tag Demo-repository:v1 487920346599.dkr.ecr.us-east-1.amazonaws.com/task_db2/Demo-repository:v1
                    docker push 487920346599.dkr.ecr.us-east-1.amazonaws.com/task_db2/Demo-repository:v1
                   
               '''
            }
        }


    }        
}
