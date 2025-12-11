// Jenkinsfile
pipeline {
    agent any 

    stages {
        stage('Checkout Code') {
            steps {
                // The 'checkout scm' step automatically clones the repo configured in the UI
                checkout scm
                echo "Repository cloned to workspace: ${env.WORKSPACE}"
            }
        }
        
        stage('Run Python Script from GitHub') {
            steps {
                echo 'Executing the Python script...'
                
                // Use the relative path to your script within the repository
                // For Linux/macOS agents
                sh 'python3 Test.py' 

                // For Windows agents, uncomment and use 'bat'
                // bat 'python addition.py' 
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed. Check the console output for errors.'
        }
    }
}
