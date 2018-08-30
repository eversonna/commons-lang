pipeline {
  agent any
  stages {
    stage('Download') {
      steps {
        git 'https://github.com/eversonna/commons-lang.git'
      }
    }
    stage('Build') {
      steps {
        bat 'mvn package'
      }
    }
    stage('Finish') {
      parallel {
        stage('Finish') {
          steps {
            echo 'You\'ve done it!'
          }
        }
        stage('Print some More') {
          steps {
            echo 'Hey'
          }
        }
      }
    }
    stage('Build Job') {
      steps {
        build 'doj-ldap-service'
        echo 'It Built!'
      }
    }
  }
}