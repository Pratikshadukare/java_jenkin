pipeline {
  agent any

  stages {
    stage('Test') {
      steps {
        script {
          sh 'sonar-scanner \
            -X \
            -D sonar.projectKey=javaPipeline \
            -D sonar.projectName=Unreal-Engine-Project1'
        }
      }
    }
    
    stage('Quality Gate') {
      steps {
        script {
          timeout(time: 1, unit: 'HOURS') {
            waitForQualityGate abortPipeline: true
          }
        }
      }
    }
    
    stage('Build') {
      steps {
        // Add your build steps here
        // For example: sh 'mvn clean install'
      }
    }
    
    stage('Deploy') {
      steps {
        // Add your deployment steps here
        // For example: sh 'kubectl apply -f deployment.yaml'
      }
    }
  }
}
