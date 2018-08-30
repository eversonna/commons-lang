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
        sh 'mvn'
      }
    }
  }
}