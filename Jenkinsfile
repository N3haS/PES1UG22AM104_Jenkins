pipeline { 
  agent any 
  stages { 
    stage('Clone repository'){
      steps {
        checkout([$class: 'GitSCM',
                  branches: [[name: '*/main']],
                  userRemoteConfigs: [[ url: 'https://github.com/N3haS/PES1UG22AM104_Jenkins.git']]])
        }
    }                        
    stage('Build') { 
      steps { 
        build 'PES1UG22AM104-1'
        sh 'g++ main1.cpp -o output'
        echo 'Build Stage Successfu' 
      } 
    } 
    stage('Test') { 
      steps { 
        sh './output' 
        echo 'Test Stage Successful' 
        }  
      }
    stage('Deploy') { 
      steps { 
        echo 'Deployment Successful' 
      } 
    }
  }
  post { 
    failure { 
      echo 'Pipeline failed' 
    } 
  }
}

