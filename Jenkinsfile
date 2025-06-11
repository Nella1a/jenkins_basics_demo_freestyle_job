#!/user/bin/env groovy

library identifier: 'jenkins-shared-library@main', retriever: modernSCM(
    [
        $class: 'GitSCMSource',
        remote: 'https://github.com/Nella1a/jenkins-shared-library.git',
        credentialsId: 'github-credentials'
    ]
)

def gv

pipeline {
    agent any
    tools {
        maven 'maven-3.9'
    }

    stages {
      stage("init") {
            steps {
                script {
                  gv = load "script.groovy"
                }
            }
      }
      stage("run tests") {
            steps {
                script {
                  gv.testApp()
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
      stage("build and push image") {
             steps {
                script {
                    buildImage 'kanjamn/demo-app:jma-3.0'
                    dockerLogin()
                    dockerPush 'kanjamn/demo-app:jma-3.0'
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
