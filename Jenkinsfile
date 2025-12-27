pipeline{
    agent any
    triggers{
        githubPush()
    }
    stages{
        stage('code checkout'){
            steps{
                git branch: 'master', url:'https://github.com/sgiridhar91/Amazon-demo.git'
            }
        }
    }
}
