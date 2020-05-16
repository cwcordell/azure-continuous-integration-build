# Azure Continuous Integration Build

## Introduction

### Jenkins Setup

To start a Jenkins container for the first time use the command below. Feel free to change the directory location to suit your needs.

```bash
JENKINS_DIRECTORY=$HOME/jenkins
docker run --name jenkins -p 8080:8080 -p 50000:50000 -v $JENKINS_DIRECTORY:/var/jenkins_home jenkins
```

Get the Jenkins password from the Jenkins environment:

```bash
JENKINS_PASSWORD_FILE=$JENKINS_DIRECTORY/secrets/initialAdminPassword
JENKINS_PASSWORD=$(cat $JENKINS_PASSWORD_FILE)
echo $JENKINS_PASSWORD_FILE
```
