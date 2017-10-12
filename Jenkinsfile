pipeline { 
    agent { 
        any
    } 
    parameters { 
        choice(choices: 'CI\nDEV\nPROD', description: 'Target Env', name: 'targetEnvironment')
        text(name: 'releaseNotes', defaultValue: 'CI Build', description: 'Release Notes')
    }
    stages {
        stage('Initialize') { 
            steps { 
                echo "params: $params" 
            }
        }
        stage('Build') { 
            steps { 
                sh 'env'
                echo "mvn clean package"
            }
        }
        stage('Test') { 
            steps { 
                echo "Running Tests"
            }
        }
        stage('Deploy') { 
            steps { 
                echo "Deployment Target: $params['targetEnvironment']" 
            }
        }
    }

}