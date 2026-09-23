pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                // For public repositories
                git branch: 'main', url: 'https://github.com/yammiesolution/Test-App'
                
                // For private repositories, attach your Jenkins credential ID
                // git branch: 'main', credentialsId: 'github-token-id', url: 'https://github.com'
            }
        }

        stage('Run Tests') {
            steps {
                // Replace with your project's specific test command
                // For Node.js/JavaScript:
                sh 'npm install && npm test'
                
                // For Maven/Java:
                // sh 'mvn test'
                
                // For Python:
                // sh 'pip install -r requirements.txt && pytest'
                
                // For Windows agents, use 'bat' instead of 'sh':
                // bat 'mvn test'
            }
        }
    }
    
    post {
        always {
            // Optional: Archive test results (e.g., JUnit XML reports)
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
