pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/train.zip'
             }
        }
        stage(DeployToStaging) {
            when {
                branch 'master'
            }
            steps {
