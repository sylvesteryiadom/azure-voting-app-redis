pipeline {
  agent any
  stages {
    stage('docker container') {
      steps {
        sh '''cd azure-vote/
docker build -t jenkins-pipeline .
docker images -a
cd ..'''
      }
    }

    stage('push container') {
      steps {
        sh '''cd azure-vote/
script {
docker.withRegistry(\'https://hub.docker.com/\', \'DockerHub\') {
def image = docker.build("sylvesteryiadom/jenkins-course:latest")
image.push()
 }
}'''
      }
    }

  }
}