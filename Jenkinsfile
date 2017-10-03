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
        deployAction = input(message: 'deploy to production?', id: 'deploy', ok: 'deploy', submitterParameter: 'approveUser', submitter: 'nham', requestTimeout: 15000)
        echo ("user input: "+userInput)
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
