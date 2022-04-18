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
                deploy adapters: [tomcat9(credentialsId: '376e01e8-e628-40d2-aaec-6452f707a3ff', path: '', url: 'http://172.31.20.211:8080')], contextPath: 'qaaapp', war: '**/*.war'
            }
        }
        stage('ContinuousTesting_Master')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /home/ubuntu/.jenkins/workspace/DeclarativePipeline1/testing.jar'
            }
        }
        stage('ContinuousDelivery_Master')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '376e01e8-e628-40d2-aaec-6452f707a3ff', path: '', url: 'http://172.31.21.226:8080')], contextPath: 'myprodapp', war: '**/*.war'
            }
        }
    }
}
