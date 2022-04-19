pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                nodejs('npm') {
                    sh 'npm install'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                nodejs('npm') {
                    sh 'npm run test'
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
