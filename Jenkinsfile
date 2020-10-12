pipeline {
 agent any
 /*
 environment {
    dotnet = 'C:\Program Files\dotnet\dotnet.exe'
 }*/

 stages {
    stage('Checkout') {
        steps {
            git credentialsId: 'dstar55', url: 'https://github.com/dstar55/DotNetHelloWorld', branch: 'master'
        }
    }

  /*
  stage('Restore PACKAGES') {
   steps {
    bat "dotnet restore --configfile NuGet.Config"
   }
  }*/
   stage('Clean') {
    steps {
     bat 'dotnet clean'
    }
   }
  
  stage('Build') {
   steps {
    bat 'dotnet build --configuration Release'
   }
  }
  
  stage('Pack') {
   steps {
    bat 'dotnet pack --output nupkgs'
   }
  }
  /*
  stage('Publish') {
   steps {
    bat 'dotnet nuget push nupkgs\\DotNetHelloWorld.1.0.0.nupkg -k 8623ee99-8cc5-30ce-9437-0964aee3eb1f -s http://localhost:8081/repository/nuget-hosted'
   }
  }*/
 }
}
