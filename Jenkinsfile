/**
 * File for the Jenkins Multibranch pipeline plugin.
 *
 * This is used in order to validate the development build and to setup
 * a basic continuous delivery process from release branches.
 * This script assumes you are using Gitflow as the branching model for your project.
 * See https://github.com/jenkinsci/pipeline-plugin/blob/master/TUTORIAL.md
 */

pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
    }
  }
  stages {

    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn -B test'
      }
    }

    /*stage('Code check') {
      steps {
        sh 'mvn -B verify'
      }
    }*/
  }
}