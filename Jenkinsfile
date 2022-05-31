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
                withAWS(AccessKeyId:'AKIA6FBAA42IJJLEX4P5',SecretAccessKey:'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') {
                    echo 'hhaaha'
                }
            }
        }
    }
}
