pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'aws deploy push --application-name my-app --s3-location s3://my-bucket/my-app.zip'
            }
        }
    }
    post {
        always {
            mail to: 'u.khayam03@gmail.com',
                 subject: "Build Status: ${currentBuild.currentResult}",
                 body: "The build status is ${currentBuild.currentResult}."
        }
    }
}
