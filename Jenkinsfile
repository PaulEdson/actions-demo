pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/PaulEdson/actions-demo', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t pauljedson/samplewebpage .'
      }
    }

    stage('docker login') {
      steps {
        sh 'docker login -u pauljedson -p dckr_pat_PMJ7sNccWxxALsdDjWJJSQuDNeI'
      }
    }

    stage('docker push') {
      steps {
        sh 'docker push pauljedson/samplewebpage'
      }
    }

  }
}
