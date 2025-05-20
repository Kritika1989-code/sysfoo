pipeline{

    agent any

    tools{
       maven 'Maven 3.6.3' 
    }

    stages{
        stage('build'){
            steps{
                echo 'this is the build job'
                mvn compile
            }
        }
        stage('test'){
            steps{
                echo 'this is the test job'
                mvn clean test
                sleep 9
            }
        }
        stage('package'){
            steps{
                echo 'this is the package job'
		mvn package -DskipTests
            }
        }
    }
    
    post{
        always{
            echo 'this pipeline has completed...'
        }
        
    }
    
}
