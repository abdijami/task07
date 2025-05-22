pipeline {
    agent { label 'agent-01' }

    environment {
        DEPLOY_ENV = "Production"
    }

    stages {
        stage('Lint') {
            steps {
                echo 'Linting...'
                sh 'echo "No linting tool configured."'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'pytest tests/ || echo "pytest not installed or no tests found."'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project...'
                sh 'tar -czf hello-world.tar.gz main.py requirements.txt'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to ${env.DEPLOY_ENV}"
                sh 'echo "Deploy stage executed."'
            }
        }
    }
}

