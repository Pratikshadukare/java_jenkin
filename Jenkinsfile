pipeline {
  agent any

  stages {
    stage('Test') {
      steps {
       //pppppppppppppppppppppppppppp
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
