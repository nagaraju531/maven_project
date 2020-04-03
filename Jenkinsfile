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
