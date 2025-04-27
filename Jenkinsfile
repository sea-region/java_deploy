pipeline {
    agent any
    stages {
        stage('Read File') {
            steps {
                script {
                    sh 'ls -ltr'
                    def fileContent = readFile 'pom.xml'
                    echo "File content: ${fileContent}" // Display the content
                    // Further process the fileContent as needed

                     def props = readProperties file: 'pom.xml'
                    echo "properties file is ${props}"
                }
            }
        }
    }
}
