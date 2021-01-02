pipeline {
  agent any
  stages {
    stage('Development Build') {
      steps {
        echo 'Pull the code from Git Hub Repository'
        echo 'Create a Build using Repo'
      }
    }

    stage('Smoke Test') {
      steps {
        echo 'Run 2 Smoke Tests'
      }
    }

    stage('Deploy in QA') {
      steps {
        echo 'Stop the Server'
        echo 'Move the build in QA Env'
        echo 'Start the Server'
        echo 'Notify to QA by Email'
      }
    }

    stage('Integration Test') {
      parallel {
        stage('Integration Test') {
          steps {
            echo 'Sanity Test (UI)'
          }
        }

        stage('API Test') {
          steps {
            echo 'Run REST Automation Test'
          }
        }

        stage('Performance Testing') {
          steps {
            echo 'Run Jmeter Tests'
          }
        }

      }
    }

    stage('Certify') {
      steps {
        echo 'QA Team Cerfity'
      }
    }

  }
}