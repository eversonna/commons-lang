pipeline {
  agent any
  stages {
    stage('Download') {
      steps {
        git 'https://github.com/eversonna/commons-lang.git'
      }
    }
    stage('Build Commons-Lang') {
      steps {
        bat 'mvn package'
      }
    }
    stage('Build DOJ ACISS Client') {
      steps {
        build 'doj-aciss-client'
      }
    }
    stage('Request Permission') {
      steps {
        input(message: 'Ready to proceed?', ok: 'OK?')
      }
    }
  }
}