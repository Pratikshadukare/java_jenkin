pipeline {
  agent any
  environment {
    SCANNER_HOME = tool 'SonarQube'
  }
  stages {
    stage('Test') {
      steps {
        withSonarQubeEnv('SonarQube') {
          sh "${SCANNER_HOME}/bin/sonar-scanner \
            -X \
            -D sonar.projectKey=javaPipeline \
            -D sonar.projectName=Unreal-Engine-Project1"
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
