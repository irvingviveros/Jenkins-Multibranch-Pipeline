pipeline {
        agent any

		environment {
			STAGE_1 = 'First'
			STAGE_2 = 'Second'
			STAGE_3 = 'Third'
			EXECUTE = 'False'
		}

                stages {
                        stage(STAGE_1) {

				EXECUTE = 'True'
                                steps {
                                        sh '''
                                                echo "Step One"
                                        '''
                                }
                        }


                        stage(STAGE_2) {
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

                        stage(STAGE_3) {
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
