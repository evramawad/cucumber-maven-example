pipeline {
    agent {
		label ''
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
post {
    always {
 cucumber failedFeaturesNumber: -1,
 fileIncludePattern: 'cucumber-json-report.json',
 jsonReportDirectory: 'target',
 reportTitle: 'cucumber-report',
 sortingMethod: 'ALPHABETICAL',
    }
}
        }
    }
}
