pipeline {
    agent any
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
		 		  
        }
		stage ('Change the new path') {
           steps {
          dir('/root/.jenkins/workspace/Packagefile/java-maven-calculator-web-app-master'){
            sh "$PWD"
          }
        } 	
	}
		    
        stage ('Build') {
            steps {
                sh 'mvn clean package'
            }
            post {
               success {
                  echo 'Now Archiving'
                  archiveArtifacts artifacts: '**/target/*.war'
               }
            }
        }
        stage ('Deploy') {
            steps {
                echo 'Hello World Deploy'
            }
        }
    }
}
