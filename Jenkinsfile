@Library('shared_library') _

import com.example.Utils

def props = Utils.loadProperties(this, 'pipeline.properties')

pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage('Build') {
            steps {
                script {
                    build(goals: props['maven_goals'])
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    test()
                }
            }
        }
        stage('SonarQube') {
            steps {
                script {
                    sonarqube(goals: props['sonar_goals'])
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    deploy(goals: props['deploy_goals'])
                }
            }
        }
    }
}
