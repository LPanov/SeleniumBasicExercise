pipeline{
    agent any
    stages{
        stage("Restore dependencies"){
            steps{
                bat 'dotnet restore'
            }
            post{
                always{
                    echo "Step executed successfully"
                }
            }
        }
        stage("Build"){
            steps{
                bat 'dotnet build --no-restore'
            }
        }
        stage("Run Tests"){
            parallel {
                stage("Run Test for Project 1"){
                    steps{
                        bat 'dotnet test TestProject1/TestProject1.csproj'
                    }
                }
                stage("Run Test for Project 2"){
                    steps{
                        bat 'dotnet test TestProject2/TestProject1.csproj'
                    }
                }
                stage("Run Test for Project 3"){
                    steps{
                        bat 'dotnet test TestProject3/TestProject1.csproj'
                    }
                }
            }
        }
    }
    post{
        always{
            echo "Workflow executed successfully"
        } 
    }
}
