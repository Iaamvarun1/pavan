pipeline{
	agent any
	
	environment {
		DEV_IP = "172.31.6.150"
	}
	stages{
		stage('SCM - Checkout'){
			steps{
				git credentialsId: 'github', url: 'https://github.com/javahometech/myweb'
			
			}
		}
		
		stage('Docker - Build'){
			steps{
			   withCredentials([string(credentialsId: 'docker', variable: 'Pwd')]) {
					sh "docker login -u admin -p ${Pwd} "
			   }
			   
			   sh "docker build . -t varun/myweb:${DOCKER_TAG} "
			}
		}
		
		stage('Docker - Push'){
			steps{
			   sh "docker push imagename "
			}
		}
		
		stage('Docker - Run'){
			steps{
      
				sh" docker run -itd 
        
			}
		}
    
    stage(" pull sample project"){
        steps{
        
        }
	
	  }
    
    stage("Run the commands"){
        steps{
        
        }
    }
    
    stage("Push SBOM to DT"){
        steps{
        
        }
    }    
  }
}  
	


def getLatestCommitId(){
	def commitId = sh returnStdout: true, script: 'git rev-parse HEAD'
	return commitId
}
