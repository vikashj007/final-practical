pipeline {
  agent any
  tools {maven 'M7'}
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/vikashj007/final-practical.git'
      }
    }
    stage('Build') {
      steps {
        bat 'mvn clean install'
      }
    }
    stage('Compile') {
      steps {
        bat 'mvn compile'
      }
    }
    stage('Test') {
      steps {
        bat 'mvn test'
      }
    }
    stage('Deploy') {
      steps {
        bat 'mvn package'
      }
    }
    stage('Result') {
      steps {
        bat 'java -cp target/ProjectA-1.0-SNAPSHOT.jar com.example.App'
      }
    }
    post {
      success {
        echo 'Jenkinsfile Pipeline Created'
      }
      failure {
        echo 'Something Wants Wrong'
      }
    }
  }
}
