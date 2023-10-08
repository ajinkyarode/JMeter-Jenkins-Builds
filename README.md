# JMeter-Jenkins-Builds

This is a complete Jenkins pipeline to showcase the CI/CD functionality

The whole CI/CD process can be divided into following steps:

Step 1:
- Develop a script in JMeter.
- Push the .jmx file along with the updated Jenkins file (to include the recent test in it) to this Repository

Step 2:
- The Jenkins pipeline is configured to be triggered for "GitHub hook trigger for GITScm polling"
- Enter the appropriate git repo credentials, the repo name and the script file (here jenkinsfile) that you want to build
- Since Jenkins has been hosted locally it is not possible to expose it to the Internet.
- In order to perform above process there is a workaround mentioned in the next step.

Step 3:
- In order to expose your localhost Jenkins server you can use use the ngrok tool and type in the command :ngrok http 8080 (or whatever port you are using for jenkins)
- ![image](https://github.com/ajinkyarode/JMeter-Jenkins-Builds/assets/14822548/19fddf78-ec37-4e58-a50f-db7301d5bc12)
- Copy the Forwarding address from the above screenshot and navigate to the GitHub

Step 4:
- In GitHub go to settings and under Webhooks enter the following address under Payload URL followed by "/github-webhook/
- ![image](https://github.com/ajinkyarode/JMeter-Jenkins-Builds/assets/14822548/9eb401a3-cccd-4fb7-806f-3385c817cf47)
- Add the webhook

Step 5:
- Now you would have the jenkins exposed to the internet
- Whenever you make any code changes that are pushed to this repo, Jenkins will take care or build and test steps and publish reports as mentioned in the script

Additional Info:
In Jenkins, the Performance Test plugin has been installed to view the trending test results in Jenkins itself.
