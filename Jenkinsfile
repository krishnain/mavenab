pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_Master')
        {
            steps
            {
                git 'https://github.com/krishnain/mavenab.git'
            }
        }
        stage('ContinuousBuild_Master')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContinuousDeployment_Master')
        {
            steps
            {
deploy adapters: [tomcat9(credentialsId: '898c13c4-28fd-4283-82d8-c07f78f8a5e8', path: '', url: 'http://172.31.6.79:8080')], contextPath: 'testapp', war: '**/*.war'
	}
        }
        stage('ContinuousTesting_Master')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /home/ubuntu/.jenkins/workspace/MultiBranchPipeline1_master/testing.jar'
            }
        }
        stage('ContinuousDelivery_Master')
        {
            steps
            {
            deploy adapters: [tomcat9(credentialsId: '898c13c4-28fd-4283-82d8-c07f78f8a5e8', path: '', url: 'http://172.31.7.39:8080')], contextPath: 'prodapp', war: '**/*.war'

	    }
        }
    }
}
