pipeline {
  agent { label 'BansariNode' }
  tools {
    maven 'M3'
  }
  stages {
    stage ('Initialize') {
      steps {
        bat '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            ''' 
      }
    }
    
    stage ('Trufflehog') {
      steps {
        bat 'C:/Users/bansarid/Documents/TruffleHog/trufflehog git https://github.com/bansarid/webapp --only-verified'
      }
    }
    
    stage ('Build') {
      steps {
      bat 'mvn clean package'
       }
    }
    
  
  }
}
