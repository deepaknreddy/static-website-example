#! groovy

def branch
def workspace
def url

pipeline
{
    agent any
    stages 
    {
        stage("Cloning the Repo")
        {
            steps
            {
                scripts {
                    branch = env.BRANCH_NAME
                    echo "We are into ${branch}"
                // echo "Hello"
                // branch = env.BRANCH_NAME
                // workspace = env.WORKSPACE
                // url = env.BUILD_URL
                // echo "Current branch is ${barnch} and current workspace is ${workspace}. url is ${url}"

                }
            }

        }

    }

}
