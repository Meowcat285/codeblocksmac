pipeline {
  agent any
  stages {
    stage('Update Packages') {
      steps {
        sh 'sudo apt-get update'
      }
    }
    stage('Install packages') {
      steps {
        sh '''sudo apt-get install libwxgtk3.0-dev
sudo apt-get install gtk2.0
sudo apt-get install automake
sudo apt-get install autoconf
sudo apt-get install m4
sudo apt-get install perl'''
      }
    }
    stage('Prepare Build') {
      steps {
        sh '''autoreconf
./configure'''
      }
    }
    stage('Build (Automake)') {
      steps {
        sh 'automake'
      }
    }
    stage('Build (Make)') {
      steps {
        sh 'make'
      }
    }
    stage('Build (Make install)') {
      steps {
        sh 'sudo make install'
      }
    }
  }
}