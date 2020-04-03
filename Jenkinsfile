pipeline {
agent any
 
stages {
   stage ("initialize") {
     steps {
        sh '''
           echo "PATH = ${PATH}"
           echo "M2_HOME = ${M2_HOME}"
           '''
         }
      }
   stage ('Build project') {
    steps {
       dir("/root/.jenkins/workspace/Packagefile/java-maven-calculator-web-app-master"){
       sh 'mvn clean compile package'
       }
     }
     post {
               success {
                  echo 'Now Archiving'
                  archiveArtifacts artifacts: '**/target/*.war'
               }
            }
        }
 stage ('Deploy for staging'){
  steps {
    build job: 'Deploy-to-staging'
  }
 }
}
}
