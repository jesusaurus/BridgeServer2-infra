# BridgeServer2-infra
Install and configure the AWS Infrastructure for the BridgeServer 2.0 application.


## Initialize a new stack
1. Deploy the infrastructure to AWS. Run `sceptre launch-stack develop bridgeserver2`

The above should create the infrastructure required for BridgeServer2, it does not actually deploy the app it only installs and configures the required AWS infrastructure for it. The AWS appilcation health check is enabled therefore the EB environment will start in an error state since the app has not been deployed. The environment status should turn green once the app is successfully deployed.

2. Check for additional bootstrapping steps in [BridgeServer2 repo](https://github.com/Sage-Bionetworks/BridgeServer2).

3. Once the infrastructure for BridgeServer2 app has been setup you can deploy the app file to the stack.


## Continuous Integration
We have configured Travis to deploy CF template updates. Travis deploys using [sceptre](https://sceptre.cloudreach.com/latest/about.html)

# Contributions

## Issues
* https://sagebionetworks.jira.com/projects/BRIDGE

## Builds
* https://travis-ci.org/Sage-Bionetworks/BridgeServer2-infra

## Secrets
* We use the [AWS SSM](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-paramstore.html) to store secrets for this project.  Sceptre retrieves the secrets using a [sceptre ssm resolver](https://github.com/cloudreach/sceptre/tree/v1/contrib/ssm-resolver) and passes them to the cloudformation stack on deployment.
