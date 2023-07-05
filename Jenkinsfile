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
                    sh'mvn test'
                }
            }
        stage('Build')
            steps {
                script{
                    sh'mvn -B package'
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