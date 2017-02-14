# Application Setup

## Install Drone
* Generate appropriate oauth application/token
* Install drone inside Rancher environment see http://github.com/cchamplin/rancher-drone-compose using the github/bitbucket oauth token
 
## Enabling Repositories
1. Log into Drone via github granting access to the oauth application
2. Select the repositories you wish to enable
3. Activate the repository

## Drone Secrets
1. In the Drone project access the "Secrets" tab
2. Add yaml configuration and generate the token
```
environment:
 RANCHER_ACCESS_KEY: <RANCHER API ACCESS KEY>
 RANCHER_SECRET_KEY: <RANCHER API SECRET KEY>
 SERVICE_NAME: <RANCHER STACK>/<APPLICATION NAME>
 RANCHER_URL: <RANCHER URL>
 SERVICE_CONTAINER: <DOCKER ACCOUNT>/gov-drupal:latest
```
3. Add token to .drone.sec file in repo
 
## Drone Configuration
1. See drone.yml file in example application
 
## Builds
* Builds start automatically when items are pushed into the repository
* Services are current started before the old one is shut down

## Mounts
* Configure the .mounts file to setup symlinks for shared storage inside your application directories
