pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/samiullah6799/mlops-se-jenkins-demo.git']])

            }
        }

        stage('Installation') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Testing') {
            steps{
                sh 'pytest test.py'
            }
        }

        stage('Deployment') {

            script {
                def branchName = ${env.BRANCH_NAME}
                Deploying(branchName)
            }
        }
    }
}


def Deploying(String branchName) {
    if (branchName == 'dev') {
        println("Deploying to UAT")
    } else {
        println("Deploying to  Production")
    }
}