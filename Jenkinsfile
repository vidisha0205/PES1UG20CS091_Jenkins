pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o task task5.cpp'
                echo 'Building succesful'
            }
        }

        stage('Test') {
            steps {
                sh './task'
                echo 'Testing successful'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deployed successfully'
            }
        }
    }

    post {
        always {
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'pipeline failed'
                }
            }
        }
}
}
