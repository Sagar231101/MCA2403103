pipeline {
    agent any

    parameters {
        string(name: 'DEPLOY_BUILD_NUMBER', defaultValue: "${env.BUILD_NUMBER}", description: 'Enter the build number to deploy')
    }

    stages {
        stage('Build') {
            when {
                branch 'development'
            }
            steps {
                echo "Running build step on branch: ${env.BRANCH_NAME}"
                sh 'echo "Building project..."'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests on branch: ${env.BRANCH_NAME}"
                sh 'echo "Running tests..."'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying build number: ${params.DEPLOY_BUILD_NUMBER}"
                    sh "echo Deploying build ${params.DEPLOY_BUILD_NUMBER}"
                }
            }
        }
    }
}
