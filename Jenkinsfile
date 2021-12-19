pipeline {
  agent {
    kubernetes {
      yaml '''
        apiVersion: v1
        kind: Pod
        spec:
          containers:
          - name: aws
            image: amazon/aws-cli
            command: ['cat']
            tty: true
      '''
    }
  }
  stages {
    stage('Who Am I') {
      steps {
        container('aws') {
          sh "aws sts get-caller-identity"
        }
      }
    }
  }
}
