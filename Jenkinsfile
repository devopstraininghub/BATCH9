pipeline {
    agent any

    stages {
	
        stage('CLONE SCM STAGE') {
            steps {
                echo 'cloning code from Git HUB'
				git branch: 'main', credentialsId: 'Githubcredentails', url: 'https://github.com/devopstraininghub/BATCH9.git'
            }
        }
		
		stage('BUILD ARTIFACT STAGE') {
            steps {
                echo 'show the source code'
				sh 'ls'
				echo 'build using maven'
				sh 'mvn clean install'
            }
        }
		
		stage('DEPLOY TO TOMCAT STAGE') {
            steps {
                echo 'deploy to tomcat application server'
				deploy adapters: [tomcat9(credentialsId: 'c1e3fdd8-f652-4c76-9f75-7265ae3f1865', path: '', url: 'http://54.197.21.209:8081/')], contextPath: 'FACEBOOK', war: '**/*.war'
            }
        }
		
    }
}
