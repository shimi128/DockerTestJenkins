node('DOTNETCORE'){
	stage('SCM'){
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/shimi128/DockerTestJenkins']]])
	}
	stage('Build'){
		try{
		sh 'dotnet build ConsoleApp1.csproj'
		}finally{
		archiveArtifacts artifacts: '*.*'
		}
	}
	stage('Test'){
		echo 'Execute unit tests'
	}
	stage('Package'){
		echo 'Zip it up'
	}
	stage('Deploy'){
		echo 'Push to deployment'
	}
	stage('Archive'){
		archiveArtifacts artifacts: '*.*'
	}
}