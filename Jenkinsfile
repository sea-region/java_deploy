@Library('shared_library') _

import org.example.Utils

pipeline {
    agent any
    stages {
        stage('Delivery Pipeline') {
            steps {
                script {

                    props = new Properties();
                    sh 'ls -ltr'
                    FileInputStream propFile = new FileInputStream("pipeline.properties");
                    props.load(propFile);
                    
                    deliveryPipeline(
                        properties: props,
                        gitRepoUrl: 'https://github.com/sea-region/java_deploy.git'
                    )
                }
            }
        }
    }
}
