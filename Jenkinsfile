pipeline {
  agent none
  stages {
    stage('Checkout Go Code') {
      agent any
      steps {
        git(url: 'https://github.com/paroksh/GoLangSecRepo.git', branch: 'master')
      }
    }
    stage('Run Source Code Review') {
      agent any
      steps{
        print('Source Code Review Running')
      }
    }
    stage('Compile Go Application') {
      agent {
        docker {image 'golang:1.12.7-alpine3.10'}
      }
      steps{
        sh 'go version'
        sh 'apt-get install git'
        sh 'go get github.com/go-sql-driver/mysql'
        sh 'go get github.com/gorilla/sessions'
        sh 'go get github.com/julienschmidt/httprouter'
        print('Copied all dependencies')
              }
    }
  }
}
