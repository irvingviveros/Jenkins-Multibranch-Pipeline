pipeline {
        agent any

		environment {
			STAGE_1 = 'First'
			STAGE_2 = 'Second'
			STAGE_3 = 'Third'
			EXECUTE = 'False'
		}

                stages {
                        stage(env.STAGE_1) {

				env.EXECUTE = 'True'
                                steps {
                                        sh '''
                                                echo "Step One"
                                        '''
                                }
                        }


                        stage(env.STAGE_2) {
				when {
					expression (env.EXECUTE == 'True')
				}
                                steps {
                                        sh '''
                                                echo "Step Two"
                                                echo "Updating Second Stage"
                                        '''
                                }
                        }

                        stage(env.STAGE_3) {
				when {
					expression (env.EXECUTE != 'True')
				}
                                steps {
                                        sh '''
                                                echo "Step Three"
                                        '''
                                }
                        }
                }
}

