pipeline {
    agent { docker { image 'python:3.14.0-alpine3.22' } }

    environment {
        YOUR_PROJECT_NAME = 'test'
        YOUR_MAIN_PACKAGE_NAME = 'main_test'
    }

    stages {
        stage('build') {
            steps {
                sh '''
                  echo "Python version:"
                  python --version
                  echo "Project name: $YOUR_PROJECT_NAME"
                  echo "Main package: $YOUR_MAIN_PACKAGE_NAME"
                '''            }
        }
    }
}
