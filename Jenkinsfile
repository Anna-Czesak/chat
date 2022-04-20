pipeline {
    agent any
    tools {nodejs "nodejs"}
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'git pull origin master'
                sh 'npm install'   
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
               
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
