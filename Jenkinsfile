pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh '''#!/bin/bash
rvm use 2.2.4
bundle install
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