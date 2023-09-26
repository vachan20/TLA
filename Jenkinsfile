pipeline {
    agent any 

        stages {
        stage('Dependencies') {
            steps {
                echo 'Fetching dependencies...'
               
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
             
            }
        }

        stage('Build') {
            steps {
                echo 'Building the binary...'
                script {
                    def ciGitHash = sh(script: 'git rev-parse HEAD', returnStdout: true).trim()
                    def ciBuildTimestamp = sh(script: 'date +"%Y-%m-%d%H:%M:%S"', returnStdout: true).trim()
                    def ciBuildBranch = env.BRANCH_NAME // This will fetch the branch name for multibranch pipelines, for regular jobs you might need to fetch it from GIT_BRANCH

                   
                }
            }
        }

 
         


        stage('Package') {
            steps {
                echo 'Packaging the binary...'
                
            }
        }

        stage('Cleanup') {
            steps {
                echo 'Cleaning up...'
               
            }
        }
    }

    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed :('
        }
    }
}
