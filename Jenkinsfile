node {
 stage('Example') {
 if (env.BRANCH_NAME == 'master') {
 echo 'I only execute on the master branch'
 } else {
 echo 'I execute elsewhere'
 }
 }
}
Declative starts with "pipeline"
pipeline {
 agent any
 stages {
 stage ('Build & Test') {
 steps {
 echo 'Buildings..'
 }
 }
 stage('Sonar Code Analysis') {
 steps {
 echo 'Testing..'
 }
 }
 stage('Package') {
 steps {
 echo 'Testing..'
 }
 }
 stage('Deploy to sandbox') {
 steps {
 echo 'Deploying....'
 }
 }
 }
 post {
 success {
 bitbucketStatusNotify(buildState: 'SUCCESSFUL')
 }
 failure {
 bitbucketStatusNotify(buildState: 'FAILED')
 }
 }
 }
}