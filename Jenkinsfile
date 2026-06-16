pipeline{
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
				sh '''
				nohup java -jar target/sauce-1.0-SNAPSHOT.jar > app.log 2>&1 &
				'''
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
