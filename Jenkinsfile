pipeline {
  agent any
  stages {
    stage('sleep') {
      steps {
        sleep 5
      }
    }
    stage('deploy approval') {
      steps {
        timeout(time: 15) {
          input(message: 'deploy to production?', id: 'deploy', ok: 'deploy', submitter: 'nham', submitterParameter: 'approveUser')
        }
        
      }
    }
    stage('deploy') {
      steps {
        sh 'echo "deploy"'
      }
    }
  }
}