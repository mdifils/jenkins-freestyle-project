pipeline {
    agent any
    tools {
        maven 'maven-3.8.6'
    }

    stages {
        stage('build') {
            steps {
                sh 'mvn clean package'
                sh 'git version || true'
                sh 'docker version || true'
                sh 'docker compose || true'
                sh 'mvn --version || true'
                sh 'java -version || true'
            }
        }
        // stage('Sonar Analysis') {
        //     steps {
        //         sh 'mvn test'
        //     }
        // }
        // stage('Release') {
        //     steps {
        //         withCredentials([string(credentialsId: 'github-token', variable: 'TOKEN')]){
        //             sh '''#!/bin/bash
        //                   TAG=$(git describe --tags | cut -d "-" -f 1)
        //                   TAG_MSG=$(git tag -l $TAG --format='%(contents)')
        //                   DATA='{
        //                     "tag_name": "'$TAG'",
        //                     "target_commitish": "main",
        //                     "name": "'$TAG'",
        //                     "body": "'$TAG_MSG'",
        //                     "draft": false,
        //                     "prerelease": false
        //                   }'
        //                   curl -X POST -d "$DATA" -H "Authorization:token $TOKEN" "https://api.github.com/repos/$REPO/releases"
        //                '''
        //         }
        //     }
        // }
        // stage('Build docker image') {
        //     steps {
        //         sh 'docker  build -t mdifils/caesar-cipher:$BUILD_ID .'
        //     }
        // }
        // stage('Publish docker image') {
        //     steps {
        //         withDockerRegistry([credentialsId: 'dockerhub', url: ""]){
        //             sh 'docker  push mdifils/caesar-cipher:$BUILD_ID'
        //         }
        //     }
        // }
        // stage('Deploy') {
        //     steps {
        //         sh 'docker version || true'
        //         sh 'git version || true'
        //     }
        // }
    }
}