# Salesforce CPQ Playground
Create a scratch org and install Salesforce CPQ. 

## Steps 
1. Create a scratch org

```sfdx force:org:create -f config/project-scratch-def.json --setalias cpq-playground --setdefaultusername```

2. Install Salesforce CPQ into scratch org:

```sfdx force:package:install --package [packageId (starts with 04t)] -w 30 -u [scratchOrgName]```

3. Get your password: 

```sfdx force:user:password:generate --targetusername <username>```

4. Authorize the calculation service in package settings

## Resources
- Get your package link [here](https://steelbrick2.force.com/latestpackages)
- 214.6 has an ID of ```3D04t610000004RhvAAE```

## TODO
- Create test data

## Issues


