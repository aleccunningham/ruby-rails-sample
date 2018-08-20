pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh '''#!/bin/bash
source ~/.rvm/scripts/rvm && rvm use --install --create ruby-2.2.1 && export > rvm.env
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