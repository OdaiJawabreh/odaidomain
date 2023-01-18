pipeline {
  agent any
  stages {

    stage('Pre Build') {
      steps {
        echo(" Pre Build Stage")
        
        sshPublisher(
            continueOnError: false, failOnError: true,
            publishers: [
                sshPublisherDesc(
                configName: "odai server",
                verbose: true,
                transfers: [
                sshTransfer(
                        execCommand:" rm -rf odaidomain"
                    ),
                    sshTransfer(
                        sourceFiles: "**/*",
                        remoteDirectory: "odaidomain",
                        execCommand:" sudo npm i"
                )
             ])
            ])
      }

    }

    stage('Build') {
      steps {
        echo("Build Stage")
         sh "echo 'we are testing jenkins commands'"
      }
    }

    stage('Test') {

      steps {
        echo("Test Stage")
      }
    }

    stage('Deploy') {
      steps {
        echo("Deploy")
      }

    }

    stage('docker build') {
      steps {
        echo("docker build")
      }
    }

    stage('Post Build') {
      steps {
        echo("Post Build Stage")
      }

    }
  }

}
