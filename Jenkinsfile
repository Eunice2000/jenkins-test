pipeline {
    agent any

    triggers {
        cron('H 0 * * *') // This schedules the job to run daily at midnight
    }

    stages {

        stage("Cleanup Workspace"){
            steps {
                cleanWs()
            }
        }
        
        stage("Checkout from SCM"){
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Eunice2000/jenkins-test'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh '''
                        // cd server-side
                        npm install
                    '''
                }
                
            }
        }

        stage('Test') {
            steps {
                echo "Test App..."
            }
        }

        stage('Deploy') {
            steps {
                 echo 'Deploying App...'
            }
        }
    }

}