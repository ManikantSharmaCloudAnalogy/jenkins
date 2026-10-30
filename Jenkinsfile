pipeline{
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel-token')
    }

    stages {
        stage('Install') {
            steps {
                dir('sample-project') {
                    bat 'npm install'
                }
            }
             
        }
        stage('Test') {
            steps {
               echo  'no test script found'
            }
             
        }
        stage('Build') {
            steps {
                dir('sample-project') {
                    bat 'npm run build'
                }
            }
             
        }
        stage('Deploy') {
            steps {
                dir('sample-project') {
                    bat 'npx vercel --prod --yes --token=%VERCEL_TOKEN%'
                }
            }
             
        }
        
    }
}