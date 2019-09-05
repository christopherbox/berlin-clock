pipeline {
    agent any
 
    tools {
        jdk 'jdk8u221'
        maven 'maven3'
    }
 
    stages {
        stage('Install') {
            steps {
                sh "mvn -U clean test cobertura:cobertura -Dcobertura.report.format=xml"
            }
	    post {
		always {
			junit '**/target/*-reports/TEST-*.xml'
		 }
            }
        }
    }
}
