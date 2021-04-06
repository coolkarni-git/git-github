pipeline {
	agent any
	stages {
		stage('Git-Checkout') {
			steps {
					echo "Cheking out from GIT repo!!";
					git 'https://github.com/coolkarni-git/git-github.git'
			}
		}
		
		stage('Build') {
			steps {
					echo "Building the checkout project!!";
					bat 'build.bat'
			}
		}
		
		stage('Quality-Gate') {
			steps {
					echo "SonarQube Quality Gate sucsessfully!!";
					/*sh exit ("1");*/
			}
		}
		
		stage('Deploy') {
			steps {
					echo "Pass!!";
			}
		}
		
	}
	post {
		always {
			echo 'This will always run'
		}
		success {
			echo 'This will run only if successfull'
		}
		failure {
			echo 'This will run only if failed'
		}
		unstable {
			echo 'This will run only if the run was marked as unstable'
		}
		changed {
			echo 'This will run only if the state of the pipeline has changed'
			echo 'For example, if the Pipeline was previously failing but is now successfull'
		}
		
	}	
	
}	
