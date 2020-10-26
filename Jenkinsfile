pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        sh 'mvn clean compile'
      }
    }

    stage('Package') {
      steps {
        echo 'Deploying....'
        sh 'mvn -DskipTests package'
        archiveArtifacts(artifacts: '**/target/*.jar', fingerprint: true)
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
}