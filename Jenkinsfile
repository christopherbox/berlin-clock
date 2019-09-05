pipeline {
    agent any
 
    tools {
        jdk 'jdk8u221'
        maven 'maven3'
    }
 
    stages {
        stage('Install') {
            steps {
                sh "mvn clean test"
            }
	    post {
		always {
			junit '***/target/*-reports/TEST-*.xml'
		 }
            }
        }
    }
}
