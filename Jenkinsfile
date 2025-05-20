pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'Building the application'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'this is the second job'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'this is the third job'
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}
