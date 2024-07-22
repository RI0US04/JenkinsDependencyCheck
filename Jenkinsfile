pipeline {
	agent any
	stages {
	    stage('Checkout') {
            steps {
                 git url: 'https://github.com/RI0US04/JenkinsDependencyCheckTest.git', credentialsId: 'GitHub-PAT'
            }
        }
		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'OWASP Dependency-Checker'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}
