pipeline {
  agent any
  stages {
    stage('sleep') {
      steps {
        sleep 5
      }
    }
    stage('') {
      steps {
        input(message: 'deploy to production?', id: 'deploy', ok: 'true', submitterParameter: 'approveUser', submitter: 'nham')
      }
    }
  }
}