pipeline{
    agent { node { label 'sonarscan'} }
    stages{
        stage('Build'){
            steps{
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