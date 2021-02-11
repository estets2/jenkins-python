pipeline {
    agent {
        docker { image 'python3:latest' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'python3 --version'
            }
        }
        stage('Environment preparation') {
            steps {
                echo "-=- preparing project environment -=-"
                // Python dependencies
                sh "pip install -r requirements.txt"
            }
        }
    }
    post {
        always {
            echo "-=- remove deployment -=-"
            sh "docker stop python-jenkins-pipeline"
        }
    }
}
