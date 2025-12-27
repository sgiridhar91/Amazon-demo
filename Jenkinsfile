

pipeline{
    agent any
    triggers{
        githubPush()
    }
    parameters{
        choice(
            name: 'ENV',
            choices: ['dev','qa','prod'],
            description: 'select environment to deploy'
        )
    }
    stages{
        stage('code checkout'){
            steps{
                git branch: 'master', url:'https://github.com/sgiridhar91/Amazon-demo.git'
            }
        }
        stage('compile the code'){
            steps{
                sh 'mvn clean compile'
            }
        }
        stage('packaging'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('backup'){
            steps {
                script{
                    
                    sh "mkdir -p /home/giridhar/jenkinsbackup/${backupFolder}"
                    sh "cp target/*.war ${backupFolder}/app_${BUILD_NUMBER}.war"
                }
            }
        }
    }
}
