pipeline {
	agent { label 'jenkins-agent' }
	tools {
		jdk 'Java17'
		maven 'Maven3'
	}
	stages {
		stage("Clenup Workspace"){
			steps {
				cleanWs()
			}
		}
		stage("Check out from SCM"){
			steps {
				git branch: 'main', credentialsId: 'github', url: 'https://github.com/shweta-byte/register-app.git'
			}
		}
		stage("Build application"){
			steps {
				sh "mvn clean package"
			}
		}
		stage("Test application"){
			steps {
				sh "mvn test"
			}
		}
	}
}

