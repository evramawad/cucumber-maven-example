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
 failedScenariosNumber: -1,
 failedStepsNumber: -1,
 fileIncludePattern: 'cucumber-json-report.json',
 jsonReportDirectory: 'target',
 pendingStepsNumber: -1,
 reportTitle: 'cucumber-report',
 skippedStepsNumber: -1,
 sortingMethod: 'ALPHABETICAL',
 undefinedStepsNumber: -1
    }
}
        }
    }
}
