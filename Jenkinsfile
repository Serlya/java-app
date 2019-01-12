pipeline {
	agent {label'cent'}
    stages {
        stage ('checkout') {
            steps {
		checkout scm
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn -f java-sample-app/pom.xml clean install' 
            }
        }
	
	stage ('Copy') {
            steps {
	 	 sh 'rm -rf /chef-repo/cookbooks/tomcat/files/*'
                sh 'mv /home/zippyops/jenkins/workspace/java-app-chef/java-sample-app/target/*.war /root/chef-repo/cookbooks/tomcat/files'
		    
            }
           }       
    }
}
