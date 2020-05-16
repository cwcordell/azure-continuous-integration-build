# Azure Continuous Integration Build

## Setup

### Prerequisites

- Azure DevOps (ADO) account
- GitHub or othe hosted Git account (i.e., Bitbucket, Azure Git, etc.)
- Sufficient permissions on the Git repository and ADO to create the hooks needed
- Fork the "azure-continuous-integration-build" repository or create your own

### Create Your First Pipeline

Within the Azure DevOps Web Portal

- Go to your ADO account and choose pipelines > pipelines from the side menu
- Click the "Create Pipeline" button
- From the "Connect" tab, select the Git host you are using
- From the "Select" tab, choose the repository of interest
- From the "Configure tab, click the "Run" button
- A build will be started with the placeholder tasks

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
