pipeline {
  agent any
  stages {
     stage('Build oms-cus-sys') {
      steps {
      
          echo '########## build starting ##########'
          bat 'mvn clean install'
          echo '########## build success ##########'
      }
    } 
     stage('Test oms-cus-sys') {
      steps {
      
          echo '########## test starting ##########'
          bat "mvn test"
          echo '########## test success ##########'
      }
    }
     stage('Deploy oms-cus-sys') {
      steps {
      
          echo '########## deploy starting ##########'
          bat 'mvn package deploy -DmuleDeploy'
          echo '########## deploy success ##########'
      }
    }
  }
}