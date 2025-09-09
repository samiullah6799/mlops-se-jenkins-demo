pipeline {
    agent any

    stages {

        stage ("Checkout") {
            steps {
                checkout scmGit(branches: [[name: '*/dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/samiullah6799/mlops-se-jenkins-demo.git']])
            }
        }

        stage ("Build") {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage ("Test") {
            steps {
                sh 'python3 test.py'
            }
        }

        stage ("Deploy") {
            steps {
                echo "Deploy to concerned Stage"
            }
        }

        
    }
}