pipeline {
    agent any

    stages {  // <-- THIS was missing
        stage("Checkout") {
            steps {
                checkout scmGit(branches: [[name: '*/dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/samiullah6799/mlops-se-jenkins-demo.git']])
            }
        }

        stage("Build") {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage("Test") {
            steps {
                sh 'python3 test.py'
            }
        }

        stage("Deploy") {
            steps {
                script {
                    def branchName = env.BRANCH_NAME
                    println("BRANCH NAME: ${branchName}")
                    deploy(branchName)
                }
            }
        }
    }
}

def void deploy(String branchName) {
    if (branchName == "dev") {
        println("Deploying to UAT")
    } else {
        println("Deploying to Production")
    }
}
