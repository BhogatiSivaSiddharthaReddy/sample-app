@Library('jenkins-shared-library') _

pipeline {

    agent any

    environment {
        IMAGE_NAME = "sample-app"
        IMAGE_TAG = "${BUILD_NUMBER}"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Image') {
            steps {
                buildImage(
                    imageName: env.IMAGE_NAME,
                    imageTag: env.IMAGE_TAG
                )
            }
        }

        stage('Scan Image') {
            steps {
                scanImage(
                    imageName: env.IMAGE_NAME,
                    imageTag: env.IMAGE_TAG
                )
            }
        }

    }
}
