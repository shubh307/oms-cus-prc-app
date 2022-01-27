pipeline {
  agent any
  stages {
    stage('Unit Test') { 
      steps {
        bat 'mvn clean test'
      }
    }
    stage('Deploy Standalone') { 
      steps {
        bat 'mvn deploy -P standalone'
      }
    }
    stage('Deploy ARM') { 
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials') 
      }
      steps {
        bat 'mvn deploy -P arm -Darm.target.name=local-4.4.0-ee -Danypoint.username='API1909'  -Danypoint.password='Shubh_Sindhi@69.5%' 
      }
    }
    stage('Deploy CloudHub') { 
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
      steps {
        bat 'mvn deploy -P cloudhub -Dmule.version=4.4.0 -Danypoint.username='API1909' -Danypoint.password='Shubh_Sindhi@69.5%' 
      }
    }
  }
}