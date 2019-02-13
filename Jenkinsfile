def n = 0 
pipeline{
agent any
stages {
	stage('Trigger') {
		
			options{
				timeout(time: 300, unit: 'MINUTES')
			}
				steps {
					echo 'Ich warte auf den Trigger'
					script{
					triggered = input message: 'Trigger gegriffen?', ok: 'Yes', 
						   parameters: [choice(choices: ['Ja','Nein'], description: '', name: 'trigger')]
					echo 'Triggered?' + triggered
					}
				}
	}

	     stage('XML-Auswertung') {
	         steps{
	            	script{
					fdbck = input message: 'Feedback da?', ok: 'Ja', 
						   parameters: [choice(choices: ['Ja','Nein'], description: '', name: 'fdbck')]
	            	}
	            	echo fdbck
	         }
	     }
	     stage('Test-Exec möglich'){
	         when { expression {fdbck == 'Ja'}
	         }
	         steps{
	             echo 'Erfolgreich'
	             echo 'Ende'
	             
	             
	         }}
	         stage('Test-Exec nicht möglich'){
	             when {expression {fdbck == 'Nein'}}
	             steps{
	                script{ 
	                    n = n +1   
	                    if(n == 1 ){
	                        echo '1'
	                    }
	                }
	             
	             
	             }
	         }
	   	stage('Trigger2') {
		
			options{
				timeout(time: 300, unit: 'MINUTES')
			}
				steps {
					echo 'Ich warte auf den Trigger'
					script{
					triggered = input message: 'Trigger gegriffen?', ok: 'Yes', 
						   parameters: [choice(choices: ['Ja','Nein'], description: '', name: 'trigger')]
					echo 'Triggered?' + triggered
					}
				}
	}

	     stage('XML-Auswertung2') {
	         steps{
	            	script{
					fdbck = input message: 'Feedback da?', ok: 'Ja', 
						   parameters: [choice(choices: ['Ja','Nein'], description: '', name: 'fdbck')]
	            	}
	            	echo fdbck
	         }
	     }
	     stage('Test-Exec möglich2'){
	         when { expression {fdbck == 'Ja'}
	         }
	         steps{
	             echo 'Erfolgreich'
	             echo 'Ende'
	             
	             
	         }}
	         stage('Test-Exec nicht möglich2'){
	             when {expression {fdbck == 'Nein'}}
	             steps{
	                script{ 
	                    n = n +1   
	                    if(n == 1 ){
	                        echo '1'
	                    }
	                }
	             
	             
	             }
	     }

}
}


