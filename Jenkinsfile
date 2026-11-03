pipeline{
  agent any

  tools{
    nodejs 'Node24'
  }

  stages{
    stage('checkout'){
          steps{
            sh 'git clone https://github.com/saiabbhiram/railway-ticket-reservation-system'
          }
    }

    stage('build'){
      steps{
        sh 'cd railway-ticket-reservation-system && npm install'
        sh 'cd railway-ticket-reservation-system && npm run build'
      }
    }
    
    stage('Test') {
      steps {
        echo 'No test cases configured. Skipping tests.'
      }
    }
  }
}
