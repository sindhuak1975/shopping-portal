pipeline {
  agent any
  stages {
    stage('compile-app') {
      steps {
        echo 'this is the compile job for nodejs'
        sh 'npm install'
      }
    }

    stage('test-app') {
      steps {
        echo 'this is the test job for nodejs'
        sh 'npm test'
      }
    }

    stage('package-app') {
      steps {
        echo 'this is the package job for nodejs'
        sh 'npm run package'
      }
    }

    stage('archive-app') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'wow pipeline for node js is ready...'
    }

  }
}