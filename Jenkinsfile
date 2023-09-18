pipeline {
    agent { label 'docker-build-node' }
    tools {
	jdk 'Java17'
	maven 'maven3'
    }
    stages{
	stage("Cleanup Workspace"){
	     steps {
	     cleanWs()
	     }
	}
	stage("Checkout From SCM"){
	     steps {
		 git branch: 'main', credentialsId: 'github', url: 'https://github.com/Prabhuk8/jenkins-ci-register-app'
	     }
	}
	stage("Build Application"){
	     steps {
		sh "mvn clean package"
	     }
	}
	stage("Test Application"){
	     steps {
		sh "mvn test"
	     }
	}
    }
}
