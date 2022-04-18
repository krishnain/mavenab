@Library('newlibraries')_
pipeline
{
    agent any
    stages
    {
        stage('Continuous Download')
        {
            steps
            {
               script
               {
                  cicd.newGit("https://github.com/krishnain/mavenab.git")
               }
            }
        }
        stage('ContinuousBuild')
        {
            steps
            {
                script
                {
                    cicd.newMaven()
                }
            }
        }
        stage('ContinuousDeploy')
        {
            steps
            {
                script
                {
                    cicd.newDeploy("http://172.31.6.79:8080","testapp")
                }
            }
        }
        stage('ContinuousTesting')
        {
            steps
            {
                script
                {
                    cicd.newGit("https://github.com/intelliqittrainings/FunctionalTesting.git")
                    cicd.newTest("DeclarativePipelinewithSharedLibrarires")
                }
            }
        }
        stage('ContinuousDelivery')
        {
            steps
            {
                script
                {
                    cicd.newDeploy("http://172.31.7.39:8080","prodapp")
                }
            }
        }
        
        
        
        
        
    }
}
