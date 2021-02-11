pipeline {
  agent {
    docker {
      image 'estets2/inbound-agent'
    }

  }
  stages {
    stage('Test') {
      steps {
        sh 'python3 --version'
      }
    }

    stage('Environment preparation') {
      steps {
        echo '-=- preparing project environment -=-'
        sh 'pip install -r requirements.txt'
      }
    }

  }
  post {
    always {
      echo '-=- remove deployment -=-'
      sh 'docker stop python-jenkins-pipeline'
    }

  }
}