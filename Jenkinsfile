pipeline {
  agent none
  stages {
    stage('Checkout Go Code') {
      agent any
      steps {
        git(url: 'https://github.com/paroksh/GoLangSecRepo.git', branch: 'master')
      }
    }
    stage('Run Source Code Review')
    {
      agent any
      steps{
            print('Source Code Review Running')
            }
    }
    stage('Compile Go Application1')
     {
      agent {
            docker {
              image 'golang'
              //for cache error
              args '-v /var/lib/jenkins/workspace/govwa:/usr/local/src -e XDG_CACHE_HOME=\'/tmp/.cache\' '
                   }
            }
      steps
      {
        sh 'go env'
        sh 'go get github.com/go-sql-driver/mysql'
        sh 'go get github.com/gorilla/sessions'
        sh 'go get github.com/julienschmidt/httprouter'
        sh 'go run app.go'
      }
    }
  }
}
