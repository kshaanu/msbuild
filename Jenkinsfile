node('wi')
   {
    stage('GIT'){
        git https://github.com/GitPracticeRepo/JenkinsBuildExample.git
    }
    stage ('nuget restore'){
    bat 'nuget restore C:\wi\workspace\msbld\JenkinsBuildExample.sln'
    
   }
   stage('path'){
   bat 'cd C:\Program Files (x86)\Microsoft Visual Studio\2017\BuildTools\MSBuild\15.0\Bin'
   }
   stage('msbuild'){
   bat 'msbuild C:\wi\workspace\msbld\JenkinsBuildExample.sln'
    }
}
-------
node('msbuild') {
    stage('scm') {
    git 'https://github.com/GitPracticeRepo/JenkinsBuildExample.git'
}
  stage('build'){
      bat label: '', script: '''nuget restore C:\\jenkins\\workspace\\pipe.net\\JenkinsBuildExample.sln
cd C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\BuildTools\\MSBuild\\15.0\\Bin 
msbuild  C:\\jenkins\\workspace\\pipe.net\\JenkinsBuildExample.sln'''
  }
}
node('msbuild'){
    stage('scm'){
        git 'https://github.com/GitPracticeRepo/JenkinsBuildExample.git'
    }
    stage('nuget'){
        bat label: '', script: '''nuget restore C:\\jenkins\\workspace\\pipe.net\\JenkinsBuildExample.sln
'''
    }
    stage('cd'){
       bat label: '', script: '''cd C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\BuildTools\\MSBuild\\15.0\\Bin 

    }
    stage('build'){
        bat label: '', script: 'msbuild C:\\jenkins\\workspace\\gol\\JenkinsBuildExample.sln'
    }
}
