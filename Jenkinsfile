pipeline {
    agent any

    stages {
        stage('echo') {
            steps {
                echo 'Hello, this is lab3'
            }
        }
        stage('create a file') {
            steps {
                sh 'echo "#!/bin/sh" > lab3script.sh'
                sh 'echo "echo \'this is from within the script\'" | tee -a lab3script.sh'
                sh 'chmod +x lab3script.sh'
            }
        }
        stage('run the file and save the output') {
            steps {
                sh './lab3script.sh > output.txt'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'output.txt', allowEmptyArchive: true
        }
    }
}
