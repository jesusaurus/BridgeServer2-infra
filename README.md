# BridgeServer2-infra
Install and configure the AWS Infrastructure for the BridgeServer 2.0 application.


## Initialize a new stack
1. Create common infrastructure. Run `sceptre launch-env common`

2. Deploy the infrastructure to AWS. Run `sceptre launch-env develop`

The above will only install and configure the required AWS infrastructure. AWS automatically deploys a sample app. You will need to deploy the app as a separate step.

3. Check for additional bootstrapping steps in [BridgeServer2 repo](https://github.com/Sage-Bionetworks/BridgeServer2).

4. Once the infrastructure for BridgeServer2 app has been setup you can deploy the app file to the stack.


## Continuous Integration
We have configured Travis to deploy CF template updates. Travis deploys using [sceptre](https://sceptre.cloudreach.com/latest/about.html)

# Contributions

## Issues
* https://sagebionetworks.jira.com/projects/BRIDGE

## Builds
* https://travis-ci.org/Sage-Bionetworks/BridgeServer2-infra

## Secrets
* We use the [AWS SSM](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-paramstore.html) to store secrets for this project.  Sceptre retrieves the secrets using a [sceptre ssm resolver](https://github.com/cloudreach/sceptre/tree/v1/contrib/ssm-resolver) and passes them to the cloudformation stack on deployment.
