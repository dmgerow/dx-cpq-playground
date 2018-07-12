# Salesforce CPQ Playground

Create a scratch org with Salesforce CPQ installed

## Steps

1. Clone repository
    - go into the new project folder in command line
        - `cd dx-cpq-playground`
2. Create Scratch org for the DX Project
    - type into command line
        - `sfdx force:org:create -f -s config/project-scratch-def.json -a dx-cpq-playground`
3. Get Salesforce CPQ Package ID
    - Go to [CPQ Installation Page](http://steelbrick2.force.com/InstallPremium)
        1. Scroll down to the 'Package Installation Links' section
        2. Under Salesforce CPQ, click on the 'Production' Installation Link
        3. In the URL of the login page, copy the ID at the end that denotes the package ID
            - it's the ID that starts with '04'
                - ex. Package 214.6 has an ID of 04t610000004RhvAAE
4. Install Salesforce CPQ Package
    - type into command line
        - `sfdx force:package:install --package [packageId] -w 30`
            - use the package id from the CPQ Installation Page as `[packageId]`
            - the `-w 30` denotes that installation will wait 30 minutes for the installation to complete after package is available.
5. Generate Password for Scratch Org
    - type into command line
        - `sfdx force:user:password:generate`
    - capture username and password for Scratch org
        - type into command line
            - `sfdx force:user:display`
        - copy username and password values
6. Open Scratch Org in Browser
    - type into command line
        - `sfdx force:org:open`
7. Authorize Calculation Service
    - In Setup > Apps > Installed Packages
        1. Click 'Configure' next to Salesforce CPQ
        2. Navigate to the 'Pricing and Calculation' tab
        3. use scratch org username and password to login for authorization of Calculation Service

## Future Improvements

- Create test data to load when creating scratch org

## Known Issues