pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: 'main']],
                    userRemoteConfigs: [[url: 'https://github.com/sandeshkumatgi/SANDESH_PES1UG22CS522_JENKINS']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'SANDESH_PES1UG22CS522-1'
                sh 'g++ main/hello.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
