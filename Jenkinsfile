node{
   stage('SCM Checkout'){
     git branch: 'main', credentialsId: 'Git', url: 'https://github.com/Nov202/Docker-image'
   }
   stage('Docker build image'){
     sh 'docker build -t image name .'
   }
   stage('Docker login'){
     withCredentials([string(credentialsId: 'dockerhub-app', variable: 'Dockerhubapp')]) {
     sh "docker login -u  -p "
   }
     sh 'docker push image name'
   }
}