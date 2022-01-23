pipeline {
  agent any

   
    stages {
        
        stage('Cleanup Workspace') {
            steps {
                cleanWs()
                sh """
                echo "Cleaned Up Workspace For Project"
                """
            }
        }

        stage('Code Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/julianNinoo/TestOrphanedJenkiks.git']]
                ])
            }
        }

        stage(' Unit Testing') {
            steps {
                sh """
                echo "Running Unit Tests"
                """
            }
        }

        stage('Code Analysis') {
            steps {
                sh """
                echo "Running Code Analysis"
                """
            }
        }
	stage("chao maquina") {
            options {
                timeout(time: 5, unit: "MINUTES")
            }

            steps {
                echo "Hola"
                sleep(time: 10, unit: "MINUTES")
            }
        }
        stage('Build Deploy Code') {
            steps {
                sh """
                echo "Building Artifact"
                """
                }        
            }
        }
}
