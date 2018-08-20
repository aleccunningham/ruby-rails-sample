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
    stage('Post') {
      parallel {
        stage('Passed Build') {
          steps {
            hipchatSend(room: 'Operations', sendAs: 'Jenkins', message: '\'$JOB_NAME #$BUILD_NUMBER $STATUS after $BUILD_DURATION (<a href="$BUILD_URL">View build</a>)', color: 'GREEN', textFormat: true, token: 'fGewBNmzji08Y2IKWmNI01vgelFf3Skp9ZtLscT6', credentialId: '4be3c228-b180-4755-ad51-588879b2536d')
          }
        }
        stage('Failed Build') {
          steps {
            hipchatSend(room: 'Operations', sendAs: 'Jenkins', message: '\'$JOB_NAME #$BUILD_NUMBER $STATUS after $BUILD_DURATION (<a href="$BUILD_URL">View build</a>)', color: 'RED', credentialId: '4be3c228-b180-4755-ad51-588879b2536d', token: 'fGewBNmzji08Y2IKWmNI01vgelFf3Skp9ZtLscT6"')
          }
        }
      }
    }
  }
}