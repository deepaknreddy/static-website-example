pipeline
{
    agent any
    stages
    {
        stage('Checkout the repo')
        {
            steps{
                checkout scm
            }
        }

        stage('Deploy to Development branch')
        {
           when {
                expression { env.BRANCH_NAME == 'development' }
            }
            steps
            {
                script
                {
                    sh 'sh /home/deepu/deployment.sh'
                }
            }
        }

        stage('Deploy to Master branch')
        {
             when {
                expression { env.BRANCH_NAME == 'master' }
            }
            steps
            {
                script
                {
                    sh 'sh /home/deepu/deployment.sh'
                }
            }
        }
    }
}
