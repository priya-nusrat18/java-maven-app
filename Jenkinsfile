#!/usr/bin/env groovy

@Library('jenkins-shared-library@master') _

pipeline {   
    agent any
    tools {
        maven 'my-maven'
    }
    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
        stage("build jar") {
            steps {
                script {
                 buildJar()

                }
            }
        }

        stage("build image") {
            steps {
                script {
                   buildImage 'priyajanasia/my-java-maven:jma-3.0'
                }
            }
        }

        stage("deploy") {
            steps {
                script {
                    gv.deployApp()
                }
            }
        }               
    }
} 
