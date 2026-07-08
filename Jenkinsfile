@Library('my-shared-library@paccar_tmp') _

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ravitips/config_file.git'
            }
        }
        stage('Prepare WS') {
            steps {
                prepareWorkspace() // Calls the prepare workspace stage
            }
        }

        stage('Build') {
            steps {
                buildStage() // Calls the build stage
            }
        }

        stage('Test') {
            steps {
                testStage() // Calls the test stage
            }
        }

        stage('Clean WS') {
            steps {
                cleanWorkspace() // Calls the clean workspace stage
            }
        }
    }
}
