pipeline {
    agent any

    stages {
        stage('testing') {
            steps {
                echo '***Hello World from test stage***'
            }
        }
        stage ('checking git'){
            steps {
                sh ('git --version')
            }
        }
        stage('aws version') {
            steps {
                echo "***stage for checking aws***"
                sh( 'aws --version' )
                sh( 'aws s3api create-bucket --bucket jenkins-bucket-ak-sk --region us-east-1' )
            }
        }
    }
}
