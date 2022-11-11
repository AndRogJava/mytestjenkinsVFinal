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
 publishHTML (target : [allowMissing: false,
 alwaysLinkToLastBuild: true,
 keepAll: true,
 reportDir: 'reports',
 reportFiles: 'myreport.html',
 reportName: 'My Reports',
 reportTitles: 'The Report'])
}
