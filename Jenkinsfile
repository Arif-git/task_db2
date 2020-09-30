node {
  stage 'Checkout'
  git 'https://github.com/Arif-git/task_db2.git'
 
  stage 'Docker build'
  docker.build('demo')
 
  stage 'Docker push'
  docker.withRegistry('https://487920346599.dkr.ecr.us-east-1.amazonaws.com/task_db2', 'ecr:us-east-1:auto-ecr-1') {
    docker.image('demo').push('latest')
  }
}
