pipeline {
  agent any
  stages {
    stage(' Dev Code Pull') {
      steps {
        echo 'Development Code pull'
      }
    }

    stage('Development Maven Build') {
      steps {
        echo 'Maven Build - Development'
      }
    }

    stage('QA Deploy') {
      steps {
        echo 'QA UI & API Deployment'
      }
    }

    stage('QA Tests') {
      parallel {
        stage('QA Tests') {
          steps {
            echo 'UI & API Testing'
          }
        }

        stage('QA UI Test') {
          steps {
            echo 'eb (Code Pull, Run tests)'
          }
        }

        stage('QA API Test') {
          steps {
            echo 'API (Code Pull, Run tests)'
          }
        }

      }
    }

    stage('QA Certification') {
      steps {
        echo 'QA to certify Yes or No (Manual)'
      }
    }

    stage('UAT Deploy') {
      steps {
        echo 'UAT Deployment'
      }
    }

    stage('UAT Certification ') {
      steps {
        echo 'UAT Cerificate Manual'
      }
    }

    stage('Prod Deploy') {
      steps {
        echo 'Production Deployment'
      }
    }

  }
}