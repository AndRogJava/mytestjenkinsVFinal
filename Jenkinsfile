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
                    
                 archive includes: 'pkg/*.gem'

        // publish html
                publishHTML target: [
                allowMissing: false,
                alwaysLinkToLastBuild: false,
                keepAll: true,
                reportDir: '/var/jenkins_home/jobs/pipeline_github1/builds',
                reportFiles: 'index.html',
                reportName: 'RCov Report'
                ]
                }
            }
        }
    }
 
}
