pipeline {
  agent none
  stages {
    stage('git') {
      parallel {
        stage('git clone') {
          steps {
            echo 'start'
            sleep 3
            sh '''#!/bin/sh

echo "hihihihi"'''
          }
        }

        stage('echo') {
          steps {
            echo 'step'
          }
        }

      }
    }

    stage('build') {
      agent any
      environment {
        USERNAME = 'hsan'
        PASSWORD = 'aaaaa'
      }
      steps {
        sh '''#!/bin/sh

${HOME}/mvn install packakge'''
      }
    }

    stage('deploy') {
      steps {
        androidApkUpload(additionalVersionCodes: '1.0.1')
      }
    }

  }
}