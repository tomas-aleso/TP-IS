pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/tomas-aleso/TP-IS', poll: true, branch: 'master')
        bat 'gradle init'
        bat 'gradle build'
        bat 'gradle compileJava'
      }
    }

    stage('Analyze') {
      steps {
        bat 'gradle sonarqube'
        bat 'gradle -i test jacocoTestReport'
      }
    }

  }
}