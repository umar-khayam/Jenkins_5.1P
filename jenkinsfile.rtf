pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the code'
                    sh 'mvn clean package'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running unit and integration tests'
                    sh 'mvn test'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Analyzing code'
                    sh 'mvn sonar:sonar'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Scanning for security vulnerabilities'
                    sh 'zap-cli quick-scan http://localhost:8080'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to staging'
                    sh 'aws deploy push --application-name my-app --s3-location s3://my-bucket/my-app.zip'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging'
                    sh 'mvn verify'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to production'
                    sh 'aws deploy push --application-name my-app --s3-location s3://my-bucket/my-app.zip'
                }
            }
        }
    }
    post {
        always {
            emailext(
                to: ‘u.khayam03@gmail.com',
                subject: "Build Status: ${currentBuild.currentResult}",
                body: "The build status is ${currentBuild.currentResult}.",
                attachmentsPattern: 'logs/*.log'
            )
        }
    }
}
