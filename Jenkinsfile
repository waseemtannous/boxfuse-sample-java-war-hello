pipeline { 
    agent any  
    stages { 
        stage('Build') {

            steps { 
                // limit to 1 minute
                timeout(time:1, unit:'MINUTES') {
                    // sh "sleep 60"
                    sh "mvn package" 
                }
            }

            post { 
                // if failed ...
                failure { 
                    echo "Build Failed"
                }

                 aborted { 
                    echo "Build Aborted"
                }
            }
        }
    }
}
// 