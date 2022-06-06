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
                    ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/.ssh/id_rsa deepu@3.109.144.127 'sudo yum install git -y && sudo service nginx stop && sudo rm -rf /usr/share/nginx/html/* && cd /opt && sudo git clone -b development https://github.com/deepaknreddy/static-website-example.git && sudo cp -pr /opt/static-website-example/* /usr/share/nginx/html/ && sudo service nginx start'
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
                    ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/.ssh/id_rsa deepu@65.2.140.149 'sudo yum install git -y && sudo service nginx stop && sudo rm -rf /usr/share/nginx/html/* && cd /opt && sudo git clone -b development https://github.com/deepaknreddy/static-website-example.git && sudo cp -pr /opt/static-website-example/* /usr/share/nginx/html/ && sudo service nginx start '
                }
            }
        }
    }
}
