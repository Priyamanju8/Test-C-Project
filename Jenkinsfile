pipeline{
	agent any
      stages{
           stage('Checkout'){
	    
               steps{
		 echo 'cloning..'
                 git 'https://github.com/Priyamanju8/Test-C-Project.git'
              }
          }
          stage("Compile"){
             
              steps{
                  echo 'compiling..'
                  bat "mvn compile"
	      }
          }
          stage('CodeReview'){
		  
              steps{
		    
		  echo 'codeReview'
                  bat 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){
		  
              steps{
	         
                  bat 'mvn test'
              }
               post {
               success {
                   junit 'target/surefire-reports/*.xml'
               }
           }	
          }
          
          stage('Package'){
		  
              steps{
		  
                bat 'mvn package'
              }
          }
	     
          
      }
}
