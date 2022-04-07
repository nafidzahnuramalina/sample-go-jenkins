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

pipeline {
    agent { dockerfile true }
    stages {
        stage("Git Clone") {
            steps {
                git branch: "${branch}", url: 'https://github.com/nafidzahnuramalina/sample-go-jenkins.git'
            }
        }
    }
}