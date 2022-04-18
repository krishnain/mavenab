@Library('newlibraries')_
pipeline
{
    agent any
    stages
    {
        stage('Continuous Download Loans')
        {
            steps
            {
               script
               {
                  cicd.newGit("https://github.com/krishnain/mavenab.git")
               }
            }
        }
        stage('ContinuousBuild Loans')
        {
            steps
            {
                script
                {
                    cicd.newMaven()
                }
            }
        }
   } 
}
