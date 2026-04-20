pipeline {
    agent any

    stages {
	
        stage('checkout') {
            steps {
                echo 'git checkout stage'
				git branch: 'main', url: 'https://github.com/chanda210-always/mindcircuit17d.git'
            }
        }

        stage('build') {
            steps {
                echo 'Building with maven '
				sh 'mvn clean install '
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to tomcat'
				deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://34.207.207.150:9080/')], contextPath: 'insta', war: '**/*.war'
				
            }
        }		
		
    }
}
