#!groovy​

pipeline {
    agent any
    parameters {
        string(name: 'namespace', defaultValue: 'prueba14', description: 'Namespace or openshift project')
        string(name: 'apiURL', defaultValue: 'https://master01.4lanr1rp12xutnpngwc0di13yb.ax.internal.cloudapp.net:8443/', description: 'Openshift API URL')
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
                openshiftCreateResource apiURL: "${apiURL}", authToken: '', jsonyaml: readFile('prueba.yml'), namespace: "${namespace}"
            }
        }
    }
}
