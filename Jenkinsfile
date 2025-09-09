pipeline {
    agent any

    stages {  // <-- THIS was missing
        stage("Checkout") {
            steps {
                echo "Repo Checkout"
            }
        }

        stage("Build") {
            steps {
                echo "Installing Dependencies"
            }
        }

        stage("Test") {
            steps {
                echo "Execution of TestCases"
            }
        }

        stage("Deploy") {
            steps {
                echo "Update being deployed to concerned stage"
            }
        }
    }
}