pipeline {
  agent any 
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
    
    stage ('Check-Git-Secrets') {
      steps {
        bat 'rm trufflehog || true'
        bat 'docker run gesellix/trufflehog --json https://github.com/bansarid/webapp.git > trufflehog'
        bat 'cat trufflehog'
      }
    }
    
    stage ('Build') {
      steps {
      bat 'mvn clean package'
       }
    }
    
  
  }
}
