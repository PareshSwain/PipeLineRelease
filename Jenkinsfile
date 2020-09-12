pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning the code..'
	git 'https://github.com/PareshSwain/maven-simple-rel.git'
            }
        }
        stage('Clean') {
            steps {
                echo 'Clean..'
		//withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	//bat "mvn -Dmaven.test.failure.ignore=true clean " //this is working in windows
		    def mvnHome = tool name: 'MAVEN', type: 'maven'
		    sh "${mvnHome}/bin/mvn clean "
        	}

            }
        }
        stage('Compile') {
            steps {
                echo 'Compiling....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	//bat "mvn -Dmaven.test.failure.ignore=true compile"
        	}
		}
		}

	stage('Test') {
            steps {
                echo 'Testing....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	//bat "mvn -Dmaven.test.failure.ignore=true test"
        	}
		}
		}

	stage('Package') {
            steps {
                echo 'Packaging....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	//bat "mvn -Dmaven.test.failure.ignore=true package"
        	}
		}
		}

stage('Deploy') {
            steps {
                echo 'deploying....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	//bat "mvn -Dmaven.test.failure.ignore=true deploy" //modified on 11-sep-2020
        	}
		}
		}
         
  
    }
}
