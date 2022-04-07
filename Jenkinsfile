pipeline{
    agent any
    environment {
        root = "/snap/bin/go"
        branch = "master"
        scmUrl = "https://github.com/nafidzahnuramalina/sample-go-jenkins.git"
    }
    stages {
        stage("Go Version") {
            steps {
                sh "${root} version"
            }
        }
        stage("Git Clone") {
            steps {
                git branch: "${branch}", url: 'https://github.com/nafidzahnuramalina/sample-go-jenkins.git'
            }
        }
        stage("Go Test") {
            steps {
                sh "${root} test ./... -cover"
            }
        }
        stage("Go Build") {
            steps {
                sh "${root} build ./..."
            }
        }
    }
}