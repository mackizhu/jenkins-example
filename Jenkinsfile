// pipeline {
//     agent any
//     environment { 
//         DEPLOY_TO = 'master'
//     }
//     stages {
//         stage('Example Build') {
//             steps {
//                 echo 'Hello World'
//             }
//         }
//         stage('Example Deploy') {
//             when {
//                 branch 'master'
//                 environment name: 'DEPLOY_TO', value: 'master'
//             }
//             steps {
//                 echo 'Deploying ${params.DEPLOY_TO}'
//             }
//         }
//     }
// }
pipeline {
    agent any
    environment { 
        DEPLOY_TO = 'master'
     }
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            when {
                expression { BRANCH_NAME ==~ /(master|staging)/ }
                anyOf {
                    environment name: 'DEPLOY_TO', value: 'master'
                    environment name: 'DEPLOY_TO', value: 'staging'
                }
            }
            steps {
                echo 'Deploying'
            }
        }
    }
}
