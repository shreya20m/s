pipline{
	agent any
	tools{
		maven 'Maven'
		}
	stages{
		stage('checkout'){
			steps{
				git branch:'master', url:'https://github.com/shreya20m/s.git'
		}
		}
		stage('build'){
			steps{
				sh 'mvn clean package'
			}
			}
		stage('test'){
			steps{
				sh 'mvn test'
			}
			}
		stage('run application'){
			steps{
				sh 'java -jar target/sauce-1.0-SNAPSHOT.jar'
			}
		}
	}
	post{
		success{
			echo 'success'
		}
		failure{
			echo 'failure'
		}
}}
