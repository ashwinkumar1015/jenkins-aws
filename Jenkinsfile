pipeline {
    agent none
    stages {
        stage('testing') {
            steps {
                echo '***Hello World from test stage***'
            }
            agent {
                docker { image 'ubuntu'}
            }
        }
        stage ('checking git'){
            steps {
                sh ('git --version')
            }
            agent {
                docker { image 'ubuntu'}
            }
        }
        stage('aws version') {
            steps {
                echo "***stage for creating bucket in aws***"
                sh( 'aws s3api create-bucket --bucket jenkins-bucket-ak-sk --region us-east-1' )
                sh( 'aws s3 ls | grep jenkins' )
                sh( 'sleep 38 ' )
                sh( 'aws s3api delete-bucket --bucket jenkins-bucket-ak-sk --region us-east-1' )
            }
            agent {
                docker { image 'aws'}
            }
        }
    }
}
