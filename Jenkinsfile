node{
   stage('SCM Checkout'){
     git branch: 'main', credentialsId: 'Git', url: 'https://github.com/Nov202/Docker-image'
   }
   stage('Docker build image'){
     sh 'sudo chown jenkins:jenkins /var/run/docker.sock'
     sh 'docker build -t umar0890/myappache5 .'
   }
   stage('Docker login'){
     withCredentials([string(credentialsId: 'dockerhub-app', variable: 'Dockerhubapp')]) {
     sh "docker login -u umar0890 -p ${Dockerhubapp}"
   }
     sh 'docker push umar0890/myappache5'
   }
}