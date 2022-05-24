pipeline {
  agent none
  environment {
    SLACK_CHANNEL = "edge"
    SLACK_TYPE = "RD"
    MAJOR_VERSION = "1"
    MINOR_VERSION = "2"
    NEXUS_REPOSITORY = "HermesGM-Edge"
    NEXUS_ARTIFACT_ID = "HermesGM-Edge"
    NEXUS_FILE_TYPE = "tar.gz"
    RELEASE_NAME = env.BRANCH_NAME.replace("/", "_") 
  }
  stages {
    stage('Testing') {
      agent {
        label "rd-ci"
      }
      steps {
        container('ci') {
          sh 'make'
        }
      }
    }
  }
  post {
    always {
    }
  }
}
