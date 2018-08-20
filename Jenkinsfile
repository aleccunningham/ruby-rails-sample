pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh '''#!/bin/bash
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