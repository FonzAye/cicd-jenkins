pipeline {
    agent { docker { image 'fonzaye/nebo:1' } }

    environment {
        YOUR_PROJECT_NAME = 'test'
        YOUR_MAIN_PACKAGE_NAME = 'main_test'
    }

    stages {
        stage('build') {
            steps {
                sh '''
                  echo "Installing git..."
                  sudo apk add --no-cache git
                  echo "Python version:"
                  python --version
                  echo "Project name: $YOUR_PROJECT_NAME"
                  echo "Main package: $YOUR_MAIN_PACKAGE_NAME"
                  echo "Cloning sample Python app:"
                  git clone https://github.com/becosta/python-sample-app.git
                  rm -rf python-sample-app/.git/
                  echo "Rename the project directory and the main package directory."
                  mv python-sample-app $YOUR_PROJECT_NAME && cd $YOUR_PROJECT_NAME
                  mv python_sample_app $YOUR_MAIN_PACKAGE_NAME
                '''            }
        }
    }
}
