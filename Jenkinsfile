#!groovy​
pipeline {
    agent any
    parameters {
        string(name: 'namespace', defaultValue: 'prueba14', description: 'Namespace or openshift project')
        string(name: 'apiURL', defaultValue: 'https://openshift.beabloo.com:8443/', description: 'Openshift API URL')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building .."
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                openshiftDeploy apiURL: "${apiURL}", authToken: '', depCfg: 'apache', namespace: "${namespace}", verbose: 'false', waitTime: '', waitUnit: 'sec'
            }
        }
    }
}
