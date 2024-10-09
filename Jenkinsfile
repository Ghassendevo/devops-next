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
          sh 'docker build -t ghassendevo/my-react-app . -f Dockerfile'
        }
      }
    }
    stage('Login') {
      steps {
        withCredentials([string(credentialsId: 'DOCKER_HUB_PASS', variable: 'DOCKER_HUB_PASS')]) {
          sh 'echo $DOCKER_HUB_PASS | docker login -u ghassendevo --password-stdin'
        }
      }
    }
     stage('Check and Push') {
            steps {
                script {
                    def imageExists = sh(script: 'docker manifest inspect ghassendevo/my-react-app:latest > /dev/null 2>&1', returnStatus: true) == 0
                    if (!imageExists) {
                        sh 'docker push ghassendevo/my-react-app:latest'
                    } else {
                        echo "Image already exists. Skipping push."
                    }
                }
            }
        }
    stage('Push') {
      steps {
        sh 'docker push ghassendevo/my-react-app:latest'
      }
    }
    stage('Run App static files'){
      steps{
        sh 'docker run -dt --name react-app -p 8003:80 ghassendevo/my-react-app'
      }
    }
  }
}
// 