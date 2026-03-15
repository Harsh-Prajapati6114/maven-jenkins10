pipeline {
    agent any
    tools {
        maven 'Maven3'
        jdk 'JAVA21'
    }
    stages {
        stage('download from github') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Harsh-Prajapati6114/maven-jenkins10.git']])
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('generate artifact') {
            steps {
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
    }
}
