pipeline {
    agent any
	tools {
		maven 'M3'
		
	}

    stages {
        stage ('Compile Stage') {

            steps {
                
                    sh 'mvn clean compile'
                
            }
        }

        stage ('Testing Stage') {

            steps {
                
                    sh 'mvn test'
                }
            }
        


        stage ('Deployment Stage') {
            steps {
                
                    deploy adapters: [tomcat8(credentialsId: 'Tomcate', path: '', url: 'http://localhost:8082/')], contextPath: 'sample-java-app', war: '**/*.war'
                }
            }
        }
    }
