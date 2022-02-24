pipeline {
  agent any
  stages {
    stage('Initializing') {
      steps {
        echo 'Initializing ...'
        sh 'echo "Working from $WORKSPACE"'
        sh '''echo "Your build number is: \\${BUILD_NUMBER} -> ${BUILD_NUMBER}"
echo "Your build number is: \\${REQUEST_ID} -> ${REQUEST_ID}"'''
      }
    }

    stage('Fetching emastercard application') {
      steps {
        echo 'Fetching emastercard-updrage-automation'
        sh '[ -d "emastercard-upgrade-automation " ] && echo "App found, skipping cloning." || git clone https://github.com/HISMalawi/emastercard-upgrade-automation.git emastercard-upgrade-automation'
      }
    }

  }
  environment {
    REQUEST_ID = 'true'
    CLUSTER_ID = '12345'
  }
}