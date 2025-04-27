@Library('shared_library') _

import org.example.Utils

pipeline {
    agent any
    stages {
        stage('Delivery Pipeline') {
            steps {
                script {

                   Properties props = new Properties();
                    sh 'ls -ltr'
                    sh 'pwd'

                File propsFile = new File(getClass().getResource('pipeline.properties').toURI())
                props.load(propsFile.newDataInputStream())
                    
                    deliveryPipeline(
                        properties: props,
                        gitRepoUrl: 'https://github.com/sea-region/java_deploy.git'
                    )
                }
            }
        }
    }
}
