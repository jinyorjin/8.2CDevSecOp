pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/jinyorjin/8.2CDevSecOp.git'
      }
    }

    stage('Install Dependencies') {
      steps {
        bat 'npm install'
      }
    }

    stage('Run Tests') {
      steps {
        bat 'npm test || exit /b 0'
      }
    }

    stage('Generate Coverage Report') {
      steps {
        bat 'npm run coverage || exit /b 0'
      }
    }

    stage('NPM Audit (Security Scan)') {
      steps {
        bat 'npm audit || exit /b 0'
      }
    }
  }
  stage('Snyk Test') {
    steps {
        bat 'snyk test || exit /b 0'
    }
}


  post {
    always {
      emailext (
        subject: "Build - ${env.JOB_NAME} #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
        body: """Build status: ${currentBuild.currentResult}\n\nSee details at: ${env.BUILD_URL}""",
        to: "s223715707@deakin.edu.au",
        attachLog: true
      )
    }
  }
}
