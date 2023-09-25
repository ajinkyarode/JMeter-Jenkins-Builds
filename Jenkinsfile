pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                echo "Cloning Repo..."
                git branch: 'main', credentialsId: '91ddaf27-3c31-43a0-b7cd-39ec5e4a248f', url: 'https://github.com/ajinkyarode/JMeter-Jenkins-Builds.git'
            }
        }
        stage('Execute Sanity Test') {
            steps {
              bat '''C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin -n -t "Demo1.jmx" -l TestRes.jtl'''
            }
        }
        stage('Execute Load Test') {
            steps {
              bat '''C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin\\jmeter -j jmeter.save.saveservice.output_format=xml -n -t C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin\\Demo5.jmx -l C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin\\demo5.jtl'''
            }
        }
        stage('Execute Regression Test') {
            steps {
              bat '''C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin\\jmeter -j jmeter.save.saveservice.output_format=xml -n -t C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin\\Demo5.jmx -l C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin\\demo5.jtl'''
            }
        }
    }
}