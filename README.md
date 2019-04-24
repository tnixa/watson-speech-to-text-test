## Test project for Watson Discovery on IBM Cloud
Just a quick project to test a Watson Discovery service instance on IBM Cloud. By default a "system" environment with its "news-en" collection can be queried. A test query will be sent and the results will be checked to see if the query appears in the results

## Setup
1. You'll need ibm cloud CLI from https://cloud.ibm.com/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install_use and bx cf installed and configured to talk to the appropriate cf org/spac etc.
2. You'll need to edit the application.properties with your own Discovery credentials

## Build
```
./mvnw package
```

## Deploy
```
bx cf push -b java_buildpack -p target/testapp-0.0.1-SNAPSHOT.jar YourAppname
```

## Verify
1. navigate to http://YourAppname.mybluemix.net/test
2. check log: 
```
bx cf logs YourAppname --recent
```