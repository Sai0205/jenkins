pipeline{
    agent { node { label 'sonarscan'} }
    stages{
        stage('Build'){
            steps{
                sh "ls"
                sh "pwd"
                echo 'Building the project...'
            }
        }
        stage('Test'){
            steps{
                echo 'Testing the project...'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying the project...'
            }
        }
    }
}