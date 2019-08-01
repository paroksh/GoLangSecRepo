pipeline {
  agent any
  stages {
    stage('Checkout Go Code') {
      steps {
        git(url: 'https://github.com/paroksh/GoLangSecRepo.git', branch: 'master')
      }
    }
  }
}