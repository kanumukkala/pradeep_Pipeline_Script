pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "Built_In Node"
                }
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "Windows_node new"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On Built_In Node') {
                    agent {
                        label "Built_In Node"
                    }
                    steps {
						echo "Task1 on Built_In Node"
					}
                }
            }
        }
    }
}
