pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh '''#!/bin/bash

source "/usr/bin/rvm"

rvm use 2.5 && bundle install
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