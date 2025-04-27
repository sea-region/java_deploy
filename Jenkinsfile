@Library('shared_library') _

import org.example.Utils

pipeline {
    agent any
    stages {
        stage('Delivery Pipeline') {
            steps {
                script {

                 
                    sh 'ls -ltr'
                    sh 'pwd'

                   def props = readProperties file: 'pipeline.properties'
                    
                    deliveryPipeline(
                        properties: props,
                        gitRepoUrl: 'https://github.com/sea-region/java_deploy.git'
                    )
                }
            }
        }
    }
}
