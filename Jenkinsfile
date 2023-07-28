pipeline {
  agent {
    node {
      label 'kubernetes'
    }

  }
  stages {
    stage('build') {
      steps {
        withMaven(maven: 'M3') {
          sh 'mvn clean install'
        }

      }
    }

    stage('result') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}