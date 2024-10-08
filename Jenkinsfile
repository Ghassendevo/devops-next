pipeline {
  agent any
 
  stages {
    stage('Build') {
      steps {
        echo "test "
      }
    }
    stage('Create Docker Image') {
      steps {
        sh 'docker build -t nextjs_docker:dev .'
        sh 'docker run --publish 3000:3000 nextjs_docker:dev'
      }
    }
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
