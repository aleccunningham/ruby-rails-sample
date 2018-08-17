pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh '''rvm use 2.5 && bundle install
'''
      }
    }
    stage('Test') {
      steps {
        sh 'rake spec'
      }
    }
  }
}