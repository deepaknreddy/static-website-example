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
                    sh 'ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/.ssh/id_rsa deepu@3.109.144.127 "/tmp/deployment.sh"'
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
                    sh 'ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/.ssh/id_rsa deepu@65.2.140.149 "/tmp/deployment.sh"'
                }
            }
        }
    }
}
