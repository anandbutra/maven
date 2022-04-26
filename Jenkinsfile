pipeline{
agent any
parameters {
  string defaultValue: 'master', description: 'pls select a branch', name: 'name', trim: true
  choice choices: ['master', 'develop', 'uat'], description: 'pls select branch', name: 'branch'
  booleanParam defaultValue: true, description: 'please select deploy', name: 'deploy'
}

stages{
stage("SCM"){
steps{
script{
    try{ echo "clone from scm is stsrted"
git branch: '$branch', credentialsId: 'github', url: 'https://github.com/anandbutra/jenkins.gt'
echo "clone from scm is completed"   }
    catch (Exception e)
    {
              echo 'Exception occurred: ' + e.toString()
        mail to: 'anandbutra@gmail.com',
    subject: "Job '${JOB_NAME}' (${BUILD_NUMBER}) is completed",
    body: "Success Please go to ${BUILD_URL} and check the buils is success or not" 
        
    }

     }
	 }
	 }
	 stage("Build"){
steps{
script{
echo "Build is stsrted"
sh 'mvn clean package'
echo "Build is completed"
     }
	 }
	 }
	  
	
	 
	 
	 }
	 }
	 
	 
                                                  
