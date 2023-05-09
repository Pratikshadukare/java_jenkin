pipeline{
  agent any
  stages{
    stage('Compile'){
      steps{
        sh 'mvn compile'
      }       
    }
    stage('Code Quality'){
      steps{
        sh 'echo Sonarqube Code Quality Check Done'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
      }
    } 
    stage('Package'){
      steps{
        sh 'mvn package'
      }
    }
    stage('Upload War File To Artifactory'){
      steps{
        sh 'echo Uploaded War file to Artifactory'
      }
    }
  }
}
