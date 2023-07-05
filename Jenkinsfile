pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
         stage('Clone repository') {
            steps {
                script{
                    checkout scm
                }
            }
        }
        stage('Test'){
            steps {
                script{
                    sh'/usr/local/bin/mvn test'
                }
            }
        }
        stage('Compile'){
            steps {
                script{
                    sh'/usr/local/bin/mvn -B package'
                }

            }

        }
        stage('Build') {
            steps {
                script{
                    app = docker.build("devops-webapp-sample")
                }
            }
        }
    }
}