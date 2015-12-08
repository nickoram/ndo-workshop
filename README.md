# Node.js Cloudant Starter Overview

The Node.js Cloudant Starter demonstrates how to use the Bluemix Cloudant NoSQL DB service. The app displays persisted files and lets the user upload new files or delete old files.

## Decomposition Instructions

* See app.js for how to obtain and use the Cloudant credentials as well as the file CRUD API
* See public/scripts/index.js and public/scripts/util.js for how the front-end calls the back-end API

## Usage

```bash
cf login -a https://api.ng.bluemix.net -u oram@ca.ibm.com -o oram@ca.ibm.com -s bootcamp

cf marketplace -s cloudantNoSQLDB			# View details for service cloudandNoSQLDB
cf create-service cloudantNoSQLDB Shared ndoCloudant
cf push ndo-workshop-manual -c "node app.js" -m 128M --no-manifest --no-start
cf bind-service ndo-workshop-manual ndoCloudant

cf start ndo-workshop-manual

cf delete ndo-workshop-manual -r
cf delete-service ndoCloudant
```
