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
            echo "params: $params" 
        }
        stage('Build') { 
            sh 'env'
            echo "mvn clean package"
        }
        stage('Test') { 
            echo "Running Tests"
        }
        stage('Deploy') { 
            echo "Deployment Target: $params['targetEnvironment']" 
        }
    }

}