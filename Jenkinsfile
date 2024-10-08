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
        withCredentials([string(credentialsId: 'tunchat123', variable: 'tunchat123')]) {
          sh 'echo "${SUDO_PASSWORD}" | sudo -S docker build -t my-react-app . -f Dockerfile'
        }
      }
    }
    stage('Push to Docker Hub') {
      environment {
        DOCKER_HUB_USERNAME = 'ghassendevo'
        DOCKER_HUB_PASSWORD = 'TunChat123'
      }
      steps {
        sh 'echo "${DOCKER_HUB_PASSWORD}" | docker login --username "${DOCKER_HUB_USERNAME}" --password-stdin'
        sh 'echo "${SUDO_PASSWORD}" | sudo -S docker push my-react-app:latest'
      }
    }
  }
}
