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
    }
    post {
        always {  
            publishHTML target: [
                reportName: 'Test',
                reportDir: 'reports',
                reportFiles: 'index.html', 
                reportTitles: 'Exec-1', 
                keepAll: true,
                alwaysLinkToLastBuild: true,
                allowMissing: false
            ]  
        }
    }
}
