pipeline {

	agent any
	stages {
		stage ('One') {
			steps {
				echo 'Building test phase'
			}
		}
		stage ('Two') {

			steps {
				input('Do you want to proceed')
			}
			
		}
		stage ('Three') {
			when {
				not {
					branch "master"
				}
			}
			steps {
				echo "Hello!"
			}
		}
		stage ('Four') {
			parallel {
				stage('Unit Test') {
					steps {
						echo "Running unit test..."
					}
				}
				stage('Integeration Test') {
					steps {
						echo "Running the integration test"
					}
				}
			}
		}
	}
}
