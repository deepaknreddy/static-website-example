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
           when
            {
                expression { env.BRANCH_NAME == 'development' }
            }
            steps
            {
                script
                {
                   sh 'ansible-playbook /etc/ansible/httpd-deployment.yml'
                }
            }
        }

        stage('Deploy to Master branch')
        {
             when
            {
                expression { env.BRANCH_NAME == 'production' }
            }
            steps
            {
                script
                {
                    sh ' ansible-playbook /etc/ansible/nginx-deployment.yml'
                }
            }
        }
    }
}
