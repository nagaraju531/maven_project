pipeline {
    agent any
    stages{
       stage('build'){
           steps {
                dir("/var/lib/jenkins/workspace/PipeLineAsCodeExample/java-maven-calculator-web-app-master"){
                 sh "pwd"
           }
            steps {
                sh 'mvn clean package'
            }
            post {
              success {
                echo "Now Archiving"
                archiveArtifacts artifacts: '**target/*.war'
                }
        }
    }
}
}
