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
	 //   stage ('Copy') {
         //   steps {
	 //	 sh 'rm -rf /etc/puppetlabs/code/environments/production/modules/war/files/*'
         //       sh 'mv /home/zippyops/jenkins/workspace/Jenkins-UpStream/java-sample-app/target/* /etc/puppetlabs/code/environments/production/modules/war/files' 
         //   }
       //    }
	stage ('Copy') {
            steps {
	 	 sh 'rm -rf /opt/chef-repo/cookbooks/tomcat/files/*'
                sh 'mv /home/zippyops/jenkins/workspace/Jenkins-UpStream/java-sample-app/target/* /chef-repo/cookbooks/tomcat/files/ 
            }
           }        
    }
}
