pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
        timeout(time: 10, unit: 'MINUTES')
        timestamps()  // Timestamper Plugin
        disableConcurrentBuilds()
    }
    triggers {
        pollSCM('H/5 * * * *')
	cron('@midnight')
    }
    stages {
        stage('Greeting') {
            steps {
                echo 'Hello, World!'
            }
        }
    }
}
