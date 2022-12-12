## replace hardcoded Id in the process builder

### add replacements snippet into sfdx-project.json

```
  {
  "packageDirectories": [
    {
      "path": "force-app",
      "default": true
    }
  ],
  "name": "HardcodedIdReplacement",
  "namespace": "",
  "sfdcLoginUrl": "https://login.salesforce.com",
  "sourceApiVersion": "55.0",
  "replacements": [
    {
      "filename": "force-app/main/default/flows/a_hardcoded_id_process_example.flow-meta.xml",
      "stringToReplace": "0011y00000Y2e6AAAR",
      "replaceWithEnv": "TARGET_ORG_ACCOUNTID"
    }
  ]
}
  
  ```



### Assign an account id value from the target org to the environment variable TARGET_ORG_ACCOUNTID 

export TARGET_ORG_ACCOUNTID = {account id in the target org}

### Run sfdx commands to replace the ids during the deployment

sfdx force:source:push


