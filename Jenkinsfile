pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh '''bundle install
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