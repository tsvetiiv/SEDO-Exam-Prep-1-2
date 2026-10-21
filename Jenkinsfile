pipeline{
    agent{
        label "node"
    }
    stages{
        stage("Restore dependencies"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                sh "dotnet restore" //Restore dependencies for MacOS
            }
        }
         stages{
        stage("Build the project"){
               when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            steps{
                sh "dotnet build --no-restore"
            }
        }
    }
         }
    stages{
        stage("Run tests"){
               when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
    }
}
}