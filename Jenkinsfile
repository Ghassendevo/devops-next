pipeline {
  agent any
 
  stages {
    stage('Build') {
      steps {
        echo "hello from ds"
      }
    }
    // stage('Create Docker Image') {
    //   steps {
    //     sh 'docker build -t my-react-app . -f Dockerfile'
    //   }
    // }
    // stage('Push to Docker Hub') {
    //   environment {
    //     DOCKER_HUB_USERNAME = 'ghassendevo'
    //     DOCKER_HUB_PASSWORD = 'TunChat123'
    //   }
    //   steps {
    //     sh 'echo "${DOCKER_HUB_PASSWORD}" | docker login --username "${DOCKER_HUB_USERNAME}"'
    //     sh 'docker push my-react-app:latest'
    //   }
    // }
  }
}