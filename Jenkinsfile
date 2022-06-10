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
                   ansible-playbook nginx-deployment.yml
                }
            }
        }
        stage ("MASTER")
        {
            when
            {
                expression{env.BRANCH_NAME=='production'}
            }
            steps
            {
                script
                {
                   sh 'ansible-playbook httpd-deployment.yml'
                }
            }
        }
        stage( "QA")
        {
          when
         {
         expression{ env.BRANCH_NAME == 'qa' }
         }
            steps
            {
                script
                {
                   echo 'QA branch '
                }
            }
        }
    }
}
