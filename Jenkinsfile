// pipeline{
//     agent any
//     environment {
//         root = "/snap/bin/go"
//         branch = "master"
//         scmUrl = "https://github.com/nafidzahnuramalina/sample-go-jenkins.git"
//     }
//     stages {
//         stage("Go Version") {
//             steps {
//                 sh "${root} version"
//             }
//         }
//         stage("Git Clone") {
//             steps {
//                 git branch: "${branch}", url: 'https://github.com/nafidzahnuramalina/sample-go-jenkins.git'
//             }
//         }
//         stage("Go Test") {
//             steps {
//                 sh "${root} test ./... -cover"
//             }
//         }
//         stage("Go Build") {
//             steps {
//                 sh "${root} build ./..."
//             }
//         }
//     }
// }

// pipeline {
//     agent {
//         docker { image 'golang-pipeline:dev' }
//     }
//     stages {
//         stage("Git Clone") {
//             steps {
//                 git branch: "${branch}", url: 'https://github.com/nafidzahnuramalina/sample-go-jenkins.git'
//             }
//         }
//     }
// }

// pipeline {
//     agent { dockerfile true }
//     stages {
//         stage('Docker') {         
//             environment {
//                 // Extract the username and password of our credentials into "DOCKER_CREDENTIALS_USR" and "DOCKER_CREDENTIALS_PSW".
//                 // (NOTE 1: DOCKER_CREDENTIALS will be set to "your_username:your_password".)
//                 // The new variables will always be YOUR_VARIABLE_NAME + _USR and _PSW.
//                 // (NOTE 2: You can't print credentials in the pipeline for security reasons.)
//                 DOCKER_CREDENTIALS = credentials('my-docker-credentials-id')
//             }

//             steps {                           
//                git branch: "${branch}", url: 'https://github.com/nafidzahnuramalina/sample-go-jenkins.git'
//             }
//         // stage("Git Clone") {
//         //     steps {
//         //         git branch: "${branch}", url: 'https://github.com/nafidzahnuramalina/sample-go-jenkins.git'
//         //     }
//         // }
//     }
//     }
// }

pipeline{
    agent any
    environment {
        branch ="master"
        scmUrl = "https://github.com/nafidzahnuramalina/sample-go-jenkins.git"
    }
    stages{
        stage("Git Clone"){
            steps{
                git branch: "${branch}", url: 'https://github.com/nafidzahnuramalina/sample-go-jenkins.git'
            }
        }
        stage("Go Dockerize"){
            steps{
                sh "docker build -t sample-go-jenkins ."
            }
        }
        stage("Deploy"){
            steps{
                echo 'Deploy Success'
            }
        }
    }
}