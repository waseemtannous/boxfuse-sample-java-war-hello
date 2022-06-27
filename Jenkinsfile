pipeline { 
    agent any  
    stages { 
        stage('Build') {

            steps { 
                // limit to 1 minute
                timeout(time:1, unit:'MINUTES') {
                    sh "mvn package" 
                }
            }

            post { 
                // if failed ...
                failure { 
                    echo "Build Failed"
                }

                // if success ...
                success { 
                    echo "Build Success"
                }
            }

        }

    }
}