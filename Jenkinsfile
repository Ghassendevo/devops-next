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
        withCredentials([string(credentialsId: 'SUDO_PASSWORD', variable: 'SUDO_PASSWORD')]) {
          // sh 'echo "${SUDO_PASSWORD}" | sudo -S docker build -t my-react-app . -f Dockerfile'
          sh 'docker build -t my-react-app . -f Dockerfile'
        }
      }
    }
    stage('Login') {
      steps {
        // withCredentials([string(credentialsId: 'DOCKER_HUB', variable: 'DOCKER_HUB')]) {
          sh 'echo TunChat123 | docker login -u ghassendevo --password-stdin'
        // }
      }
    }
    stage('Push') {
      steps {
        sh 'docker push my-react-app:latest'
      }
    }
  }
}
