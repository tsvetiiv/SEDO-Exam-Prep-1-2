
pipeline {
    agent any

    stages {
        stage("Restore dependencies") {
            when {
                anyOf {
                    branch "main"
                    branch "feature"
                }
            }
            steps {
                sh "dotnet restore"
            }
        }

        stage("Build the project") {
            when {
                anyOf {
                    branch "main"
                    branch "feature"
                }
            }
            steps {
                sh "dotnet build --no-restore"
            }
        }

        stage("Run tests") {
            when {
                anyOf {
                    branch "main"
                    branch "feature"
                }
            }
            steps {
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}
