pipeline {
    agent ( label 'docker-node')
    tools {
	jdk 'Java17'
	maven 'Maven3'
    }
    stages
	stage ("Cleanup Workspace"){
	     steps {
	     cleanWs()
	     }
	}
	stage ("Checkout From SCM"){
	     steps {
		 git branch: 'main', credentialsId: 'github', url: 'https://https://github.com/Prabhuk8/jenkins-ci-register-app'
	     }
	}
	stage ("Build Application"){
	     steps {
		sh "mvn clean package"
	     }
	}
	stage ("Test Application"){
	     steps {
		sh "mvn test"
	     }
	}
    }
}
