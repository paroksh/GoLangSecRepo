pipeline {
  agent none
  stages {
    stage('Checkout Go Code') {
      steps {
        git(url: 'https://github.com/paroksh/GoLangSecRepo.git', branch: 'master')
      }
    }
    stage('Run Source Code Review') {
      steps{
        print('Source Code Review Running')
      }
    }
    stage('Compile Go Application') {
      agent {
        docker {image 'golang:1.12.7-alpine3.10'}
      }
      steps{
        sh 'go --version'
              }
    }
  }
}
