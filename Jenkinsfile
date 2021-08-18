pipeline {
    agent any
    agent none
    stages {
        stage('Build') {
        stage('Back-end') {
            agent {
                docker {
                    image 'gradle:6.7-jdk11'
                    // Run the container on the node specified at the top-level of the Pipeline, in the same workspace, rather than on a new node entirely:
                    reuseNode true
                }
                docker { image 'maven:3.8.1-adoptopenjdk-11' }
            }
            steps {
                sh 'gradle --version'
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:14-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
