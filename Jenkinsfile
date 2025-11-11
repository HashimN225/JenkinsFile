pipeline {
    agent any      // Run this pipeline on any available Jenkins agent/node
    environment{
        ENVIRONMENT = 'Tests'
    }
    parameters{
        // string(name:'ENVIRONMENT',defaultValue:'',description:'') // One type of parameters
        choice(name:'ENVIRONMENT',choices:['Tests','Deploy'],description:'')
    }
    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pulling code from GitHub repository...'
                git branch: 'main', url: 'https://github.com/HashimN225/SSH-connect-repo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project (HTML file)...'
                sh 'ls'   // List all files (just to confirm hello.html exists)
            }
        }

        stage('Tests') {
            when{
                expression{
                    params.ENVIRONMENT =='Test'// added params. bcz we r going to use parameters
                }
            }
            steps {
                echo 'Running simple test...'
                sh 'cat hello.html'   // Print the contents of your hello.html
                sh 'python3 --version'
                sh 'python3 hello.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Simulating deployment step...'
                echo 'Hello World HTML file deployed successfully!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check logs.'
        }
    }
}
