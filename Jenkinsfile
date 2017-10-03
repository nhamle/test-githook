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
        input(message: 'deploy to production?', id: 'deploy', ok: 'deploy', submitterParameter: 'approveUser', submitter: 'nham')
      }
    }
    stage('deploy') {
      steps {
        parallel(
          "deploy": {
            sh 'echo "deploy"'
            
          },
          "deploy abort": {
            sh 'echo \'abort\''
            
          }
        )
      }
    }
  }
}
