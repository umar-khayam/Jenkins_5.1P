pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code'
                //sh 'mvn clean package'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Unit and Integration Tests'
                //sh 'mvn test'
                //sh 'mvn integration-test'
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Code Analysis'
                //sh 'mvn sonar:sonar'
            }
        }
    
        stage('Security Scan') {
            steps {
                echo 'Security Test'
                //sh 'snyk test'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application'
                //sh 'scp -i /path/to/key /path/to/your/app.jar user@${STAGING_SERVER}:/path/to/deploy'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Integration Tests on Staging'
                //sh 'ssh -i /path/to/key user@${STAGING_SERVER} "integration-tests.sh"'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production'
                //sh 'scp -i /path/to/key /path/to/your/app.jar user@${PRODUCTION_SERVER}:/path/to/deploy'
                //sh 'ssh -i /path/to/key user@${PRODUCTION_SERVER} "deploy-script.sh"'
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

//testing the pipline
