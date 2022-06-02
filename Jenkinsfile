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
                echo "Hello"
                branch = "$BRANCH_NAME"
                workspace = "$WORKSPACE"
                url = "$BUILD_URL"
                echo "Current branch is $barnch and current workspace is $workspace. url is $url"
            }

        }

    }

}
