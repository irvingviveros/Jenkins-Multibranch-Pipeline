pipeline {
	agent any
		stages {
			stage('first') {
				
						
				steps {
					sh '''
						echo "Step -One"
					'''
					script {
						env.EXECUTE = "True"
					}
				}
			}


			stage('second') {
				when {
					expression { EXECUTE == "True"}
				}
				steps {
					sh '''
						echo "Step -Two"
						echo "Updating Second Stage"
					'''
					script {
						echo "${EXECUTE}"
					}
				}
			} 

			stage('third'){
				when {
					expression { EXECUTE == "False"}
				}
				steps {
					sh '''
						echo "Step -Three"
					'''
				}
			}
		}
}
