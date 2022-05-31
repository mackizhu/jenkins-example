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
                withAWS(credentials:'aws-key') {
                    AWS("--region=eu-east-1 s3 ls")
                }
            }
        }
    }
}
