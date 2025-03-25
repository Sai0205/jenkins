pipeline{
    agent { node { label 'sonarscan'} }
     environment { 
        USER = 'sivakumar'
    }
      parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages{
        stage('Build'){
            steps{
                echo 'Building the project...'
                sh '''
                    echo "Hello ${PERSON}"
                    echo "Biography: ${BIOGRAPHY}"
                    echo "Toggle: ${TOGGLE}"
                    echo "Choice: ${CHOICE}"
                    echo "Password: ${PASSWORD}"
                '''

            }
        }

        stage( 'example'){
            environment {
                AUTH = credentials('sonar')
            }
            steps {
                sh 'printenv'
            }
        }

        stage('Input') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
            }
        }
        stage('PROD Deploy'){
            when {
                environment name: 'USER', value: 'sivakumar'
            }
            steps{
                echo "deploying to PROD"
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
                echo 'hi'
            }
        }
    }
}