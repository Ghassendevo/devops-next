pipeline {
  agent any
 
  stages {
    stage('Build') {
      steps {
        echo "hello sssssdfsdfs ds"
      }
    }
    stage('Create Docker Image') {
      steps {
        sh 'sudo docker build -t my-react-app . -f Dockerfile'
      }
    }
    stage('Push to Docker Hub') {
      environment {
        DOCKER_HUB_USERNAME = 'ghassendevo'
        DOCKER_HUB_PASSWORD = 'TunChat123'
      }
      steps {
        sh 'echo "${DOCKER_HUB_PASSWORD}" | docker login --username "${DOCKER_HUB_USERNAME}"'
        sh 'sudo docker push my-react-app:latest'
      }
    }
  }
}