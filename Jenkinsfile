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
                  echo "Python version:"
                  python --version
                  echo "Project name: $YOUR_PROJECT_NAME"
                  echo "Main package: $YOUR_MAIN_PACKAGE_NAME"
                  ls -a
                  rm -rf nebo-python-app
                  rm -rf test
                  echo "Cloning sample Python app:"
                  git clone https://github.com/FonzAye/nebo-python-app.git
                  rm -rf nebo-python-app/.git/
                  echo "Rename the project directory and the main package directory."
                  mv nebo-python-app $YOUR_PROJECT_NAME && cd $YOUR_PROJECT_NAME
                  echo "starting app"
                  pip install -e .
                  nebo-sample-app
                '''            }
        }
    }
}