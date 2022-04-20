pipeline {
    agent any
  tools {nodejs "nodejs"}
    stages {
        stage('Build') { 
            steps {
                echo 'Building'
                nodejs('npm') {
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }
        stage('Test') { 
            steps {
                echo 'Testing'
                nodejs('npm') {
                    sh 'npm run test'
                }
            }
        }
    }

    post {
        failure {
            echo 'Success'
            emailext attachLog: true,
                body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}",
                recipientProviders: [developers(), requestor()],
                to: 'czeslave2@gmail.com',
                subject: "Succesful build in Jenkins CI"
        }
        success {
            echo 'Fail'
            emailext attachLog: true,
                body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}",
                recipientProviders: [developers(), requestor()],
                to: 'czeslave2@gmail.com',
                subject: "Failed build in Jenkins CI"
        }
    }
}
