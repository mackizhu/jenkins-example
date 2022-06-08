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
// pipeline {
//     agent any
//     environment { 
//         DEPLOY_TO = 'master'
//      }
//     stages {
//         stage('Example Build') {
//             steps {
//                 echo 'Hello World'
//             }
//         }
//         stage('Example Deploy') {
//             when {
//                 expression { BRANCH_NAME ==~ /(master|staging)/ }
//                 anyOf {
//                     environment name: 'DEPLOY_TO', value: 'master'
//                     environment name: 'DEPLOY_TO', value: 'staging'
//                 }
//             }
//             steps {
//                 echo 'Deploying'
//             }
//         }
//     }
// }
pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'

                script {
                    def browsers = ['chrome', 'firefox']
                    for (int i = 0; i < browsers.size(); ++i) {
                        echo "Testing the ${browsers[i]} browser"
                    }
                }
            }
        }
    }
}

