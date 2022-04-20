pipeline{
    agent any
    /*tools {
        dotnet: 'dotnetjenkins'
    }*/
    stages{
        stage('git-pull')
        {
            steps{
                git credentialsId: 'GitHubCreds', url: 'https://github.com/mtalhatahir/run-aspnetcore-realworld.git'
            }
        }
        /*
        stage('Restore-Project')
        {
            steps{
                bat 'dotnet restore'
            }
        }
        stage('Build')
        {
            steps{
                bat 'dotnet build'
            }
        }*/
        stage('Deploy')
        {
            steps{
                sshagent(['laptop-perl1b68']) {
                sh '''ssh -tt -o StrictHostKeyChecking=no laptop-perl1b68\talha@192.168.0.100 "dir"
                
                '''
                }
            }
        }
        
    }
}