node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("cykim43/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}

stage('Build image') {
  app = docker.build("cykim43/flask-example")
}

stage('Push image') {
  docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') 
  {
     app.push("${env.BUILD_NUMBER}")
     app.push("latest")
  }
}

