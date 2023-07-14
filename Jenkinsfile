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
                echo "***stage for creating bucket in aws***"
                sh( 'aws s3api delete-bucket --bucket jenkins-bucket-ak-sk --region us-east-1' )
                zsh( 'aws s3api create-bucket --bucket jenkins-bucket-ak-sk --region us-east-1' )
                sh( 'aws s3 ls | grep jenkins' )
            }
        }
    }
}
