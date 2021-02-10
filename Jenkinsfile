#!groovy

pipeline {
    agent any
    tools {docker "docker"}

#    agent {
#        docker {
#            image 'python'
#        }
#    }
    
    stages {
        stage('Environment preparation') {
            steps {
                echo "-=- preparing project environment -=-"
                // Python dependencies
                sh "pip install -r requirements.txt"
            }
        stage('Initialize docker'){
                def dockerHome = tool 'docker'
                env.PATH = "${dockerHome}/bin:${env.PATH}"
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
