pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o pes1ug20cs151_1 pes1ug20cs152_1.cpp' // build the project using maven
                echo 'Build stage successful'
            }
        }

        stage('Test') {
            steps {
                sh './pes1ug20cs151_1'// run unit tests using maven
                echo 'Test stage successful'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment successful'
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
