pipeline{
 agent slave1
    stages{
	   stage('checkout'){
	     steps{
		    git 'https://github.com/grvsobha/DevOpsClassCodes.git'
		 }
	   }
	   stage('compile'){
	     steps{
		    sh 'mvn compile'
		 }
	   }
	   stage('codeReview'){
	     steps{
		   sh 'mvn pmd:pmd'
		 }
       }
       stage('UnitTest'){
          steps{
           sh 'mvn test'
       	  }
       }
       stage('metricCheck'){
         steps{
          sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
         }
       }
       stage('package'){
         steps{
           sh 'mvn package'
         }
       }
    }
}	
			
		   
