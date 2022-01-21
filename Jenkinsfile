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
  
	stage('Tirarme la maquina') {
            steps {
                sh """
                i=0
		while :
		do
    	 	    echo $i
    		    ((i++))
    		    if [ $i -gt 1100000000 ]
    	            then
        	        break
    		    fi
		done
		echo "Finaliza con $i"
                """
            }
        }
        stage('Build Deploy Code') {
            when {
                branch 'develop'
            }
            steps {
                sh """
                echo "Building Artifact"
                """

                sh """
                echo "Deploying Code"
                """
            }
        }

    }   
}
