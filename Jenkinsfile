pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "Windows_node new"
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
                stage('Test On Windows_node new') {
                    agent {
                        label "Windows_node new"
                    }
                    steps {
						echo "Task1 on Windows_node new"
					}
                }
            }
        }
    }
}
