#! groovy
pipeline
{
    agent any
    stages
    {
        stage("DEVELOPMENT")
        {
            when
            {
                expression{ env.BRANCH_NAME == 'development'}
            }
            steps
            {
                script
                {
                  sh 'ansible-playbook /etc/ansible/nginx-deployment.yml'
                }
            }
        }
        stage ("MASTER/PRODUCTION")
        {
            when
            {
                expression{env.BRANCH_NAME=='production'}
            }
            steps
            {
                script
                {
                   sh 'ansible-playbook /etc/ansible/httpd-deployment.yml'
                }
            }
        }
        stage( "uat")
        {
          when
         {
         expression{env.BRANCH_NAME == 'uat'}
         }
            steps
            {
                script
                {
                   echo 'UAT branch '
                }
            }
        }
    }
}
