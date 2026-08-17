pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application...'

                bat '''
                    if exist index.html (
                        echo TEST PASSED
                    ) else (
                        echo TEST FAILED
                        exit /b 1
                    )
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'

                bat '''
                    if not exist C:\\JenkinsDeployment mkdir C:\\JenkinsDeployment
                    copy /Y index.html C:\\JenkinsDeployment\\index.html
                '''
            }
        }

    }
}