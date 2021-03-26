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
                
                   deploy adapters: [tomcat8(credentialsId: 'manager-script', path: '', url: 'http://3.142.142.31:8085/')], contextPath: 'sample', onFailure: false, war: 'target\\*.war'
                }
            }
        }
    }
