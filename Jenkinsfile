pipeline {
    agent any
    parameters{
        string(name:"SOLUTIONNAME",defaulltValue:"SampleApi.sln")
    }
    stages {
        stage('Build') {
            steps {
                bat 'dotnet build %params.SOLUTIONNAME% -p:configuration=release -v:n'   
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
                    bat 'dotnet SampleApi/bin/Debug/netcoreapp2.2/SampleApi.dll'
                }
                
                
       }
}
