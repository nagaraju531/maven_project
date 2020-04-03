pipeline {
agent any
 
tools{
maven 'maven 3'
jdk 'java 8'
}
 
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
sh 'mvn clean verify
 
}
}
}
