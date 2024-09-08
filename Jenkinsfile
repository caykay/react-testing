pipeline {

  tools {nodejs "node"}

  agent {
    label 'linux'
  }

  stages {
    stage('Start React Testing') {
      when {
        anyOf {
          changeset "examples/**/**"
        }
      }

      stages {
        stage("Install npm packages") {
          steps {
            sh 'npm ci'
          }
        }

        stage("run test:actions") {
          when {
            changeset "./examples/NavBar/NavBar.actions.test.js"
          }
          steps {
            sh 'rpm run test:actions'
          }
        }

        stage("run test:reducer") {
          when {
            changeset "./examples/NavBar/NavBar.reducer.test.js"
          }
          steps {
            sh 'rpm run test:reducer'
          }
        }

        stage("run test:component") {
          when {
            changeset "./examples/Button/Button.test.js"
          }
          steps {
            sh 'rpm run test:component'
          }
        }

        stage("run test:function") {
          when {
            changeset "./examples/add/add.test.js"
          }
          steps {
            sh 'rpm run test:function'
          }
        }

        stage("run test:redux") {
          when {
            changeset "./examples/NavBar/*.test.js"
          }
          steps {
            sh 'rpm run test:redux'
          }
        }

        stage("run test:react") {
          when {
            changeset "./examples/{NavBar,Button}/*.test.js"
          }
          steps {
            sh 'rpm run test:react'
          }
        }
      }
    }
  }
}
 
 
 
 
 
