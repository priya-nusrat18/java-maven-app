#!/usr/bin/env groovy

@Library('jenkins-shared-library@jenkins-SL-new') _

pipeline {
    agent any

    tools {
        maven 'my-maven'
    }

    stages {
        stage('Build Jar') {
            steps {
                script {
                    buildJar()
                }
            }
        }

        stage('Build and Push Image') {
            steps {
                script {
                    buildImage('priyajanasia/my-java-maven:jma-3.0')
                    dockerLogin()
                    dockerPush('priyajanasia/my-java-maven:jma-3.0')
                }
            }
        }
    }
}