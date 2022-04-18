pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_Loans')
        {
            steps
            {
                git 'https://github.com/krishnain/mavenab.git'
            }
        }
        stage('ContinuousBuild_Loans')
        {
            steps
            {
                sh 'mvn package'
            }
        }
    }
}
