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
              bat '''C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin\\jmeter.bat -j jmeter.save.saveservice.output_format=xml -n -t "Demo1.jmx" -l TestReslt1.jtl'''
            }
        }
        stage('Execute Load Test') {
            steps {
              bat '''C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin\\jmeter.bat -j jmeter.save.saveservice.output_format=xml -n -t "Demo.jmx" -l TestReslt.jtl'''
            }
        }
        stage('Execute Regression Test') {
            steps {
              bat '''C:\\Users\\ajink\\Downloads\\apache-jmeter-5.6.2\\apache-jmeter-5.6.2\\bin\\jmeter.bat -j jmeter.save.saveservice.output_format=xml -n -t "Demo5.jmx" -l **/*.jtl'''
            }
        }
    }
}