pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('medalman')
	}

	stages {

		stage('Build') {

			steps {
				sh 'docker build -t Astro-X/nodeapp:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-Eteyen@1983'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push Astro-X/nodeapp:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}







