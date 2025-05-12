pipeline{
    agent any
    environment{
        DIRECTORY_PATH = "specified directory"
        TESTING_ENVIRONMENT = "Testing Environment"
        PRODUCTION_ENVIRONMENT = "Milan"
    }
    stages{
        stage('Build'){
            steps{
                echo "Fetch the source code from $DIRECTORY_PATH"
                echo "Compile the code and generate any necessary artefacts."
            }
            post{
                always{
                    mail to: "milanbhlon@gmail.com",
                    subject: "Build status email",
                    body: "Build log attached!"
                }
            }
        }
        stage('Test'){
            steps{
                echo "Unit Tests."
                echo "Integration Tests."
            }
        }
        stage('Code Quality Check'){
            steps{
                echo "Check the quality of the code."
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploy the application to $TESTING_ENVIRONMENT"
            }
        }
        stage('Approval'){
            steps{
                sleep 10
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Code has been successfully deployed to $PRODUCTION_ENVIRONMENT"
            }
        }
        stage('Complete'){
            steps{
                echo "Completed"
            }
        }
    }
}
