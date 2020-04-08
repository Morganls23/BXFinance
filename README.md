# BXFinance
## This server profile is the basis of the BXFinance Demo - Currently the `docker-compose` version

### Pre-Requisites

* Access to a Scalr Box with an External IP
* Access to a DNS domain pointing to the External IP of your Scalr Box
* Add via `etc/hosts` the following hostnames: `pingfederate pingaccess pingdataconsole pingdirectory pingdatagovernance pingdatapap` pointing to the IP address of your Scalr box

## Step By Step

1. Clone [BXFinance] (https://github.com/Technical-Enablement-PingIdentity/BXFinance.git)
2. Make environment variable changes as needed
3. Run `docker-compose up -d` under `BXFinance` root directory

## Administrator Access - PingSoftware

* Access [PingFederate] (https://pingfederate:9999/pingfederate/app)
  - administrator / 2FederateM0re
* Access [PingAccess] (hhttps://pingaccess:9000/login)
  - administrator / 2FederateM0re
* Access [PingDirectory] (http://pingdataconsole:8080/console/login)
  - pingdirectory:636
  - administrator / 2FederateM0re
  - Via Apache: ldaps://pingdirectory:1636
  - cn=dmanager / 2FederateM0re
* Access [PingDataGovernance] (http://pingdataconsole:8080/console/login)
  - pingdatagovernance:636
  - administrator / 2FederateM0re
* Access [PingDataGovernancePAP] (https://pingdatapap:9443/)
  - admin / password123

## Administrator Access - SaaS Services
* Access [P14E-PID Administration](https://admin.pingone.com/web-portal/login)
  - Use your own creds to login
* Access [MailTrap] (https://mailtrap.io/)
  - rlyle+bxfinance@pingidentity.com / 2FederateM0re

## Basic User Testing 




  


