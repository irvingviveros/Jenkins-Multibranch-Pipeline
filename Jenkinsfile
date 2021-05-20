pipeline {
        agent any

		environment {
			EXECUTE = 'False'
		}

                stages {
                        stage('First') {

				EXECUTE = 'True'
                                steps {
                                        sh '''
                                                echo "Step One"
                                        '''
                                }
                        }


                        stage('Second') {
				when {
					expression (EXECUTE == 'True')
				}
                                steps {
                                        sh '''
                                                echo "Step Two"
                                                echo "Updating Second Stage"
                                        '''
                                }
                        }

                        stage('Third') {
				when {
					expression (EXECUTE != 'True')
				}
                                steps {
                                        sh '''
                                                echo "Step Three"
                                        '''
                                }
                        }
                }
}
