pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'dotnet build SampleApi.sln -p:configuration=release -v:n'   
            }
        }
        stage('Test'){
          steps  {
                bat 'dotnet test'
          }
       }
       stage('Publish'){
          steps  {
                bat 'dotnet publish'
          }
          
       }
      
    }
     post{
                always{
                    archiveArtifacts '**'
                  
                }
                
                
       }
}
