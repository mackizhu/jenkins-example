@Library('github.com/releaseworks/jenkinslib') _

pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    echo 'mvn deploy'
                }
            }   
        }
        
        
        stage ('List S3 buckets') {
            steps {
                withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'aws-key', usernameVariable: 'AKIA6FBAA42IGCMILCHO', passwordVariable: 'Kibm81ZCsuTxz9GF4ZtKQw/1c9nNEMGV/uLOPTiF']]) {
                    AWS("--region=eu-east-1 s3 ls")
                }
            }
        }
    }
}
