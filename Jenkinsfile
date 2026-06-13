@Library('jenkins-shared-library') _

pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Docker Build') {
            steps {
                buildImage()
            }
        }

        stage('Security Scan') {
            steps {
                scanImage()
            }
        }

    }

}
