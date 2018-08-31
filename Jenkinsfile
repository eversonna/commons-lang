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
    stage('Build Supporting Jobs') {
      parallel {
        stage('Build DOJ LDAP Service') {
          steps {
            build 'doj-ldap-service'
          }
        }
        stage('Build DOJ ACISS Client') {
          steps {
            build 'doj-aciss-client'
          }
        }
        stage('Build DOJ Reports Service') {
          steps {
            build 'doj-reports-service'
          }
        }
      }
    }
    stage('Request Permission') {
      steps {
        input(message: 'Ready to proceed?', ok: 'OK?')
      }
    }
  }
}