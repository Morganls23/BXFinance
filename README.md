# BXFinance
## This server profile is the basis of the BXFinance Demo - Currently the `docker-compose` version. K8s version planned for a later release.

**NOTE:** Any branch other than master is for our SDLC and is NOT considered stable. Clone command below is recommended. All pull requests will be ignored unless previously agreed collaboration is in place.

### Pre-Requisites

**This is just one option. Ultimately you just need your own host name pointing to where ever you choose to run this, which could be localhost on your laptop.
* Access to a Scalr Box with an External IP
* Access to a DNS domain pointing to the External IP of your Scalr Box
* Add via `etc/hosts` the following hostnames: `pingfederate pingaccess pingdataconsole pingdirectory pingdatagovernance pingdatapap` pointing to the IP address of your Scalr box

## Step By Step

1. Clone [BXFinance] `git clone --single-branch --branch master https://github.com/Technical-Enablement-PingIdentity/BXFinance.git`
2. Make environment variable changes as required in env_vars file.
3. Run `docker-compose up -d` under `BXFinance` root directory
4. Note that PingAccess proxies everything in BXFinance, including the React app.

## Administrator Access - PingSoftware

* Access [PingFederate] (https://pingfederate:9999/pingfederate/app)
  - administrator / 2FederateM0re
* Access [PingAccess] (https://pingaccess:9000/login)
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

## Pre-requisites: External Services
* You need a P14E tenant with a PID SDK app.
  - Update the PingFed PID SDK adapter accordingly with your properties file from P14E.
* In that P14E tenant, you need 2 test users for the partner (AnyWealth Advisor) and workforce (Marketing) federation into BXFinance for consent enforcement.
* The partner's AnyWealth Advisor app connection to PingFed needs the following attributes,
  - subject
  - FirstName
  - LastName
  - Email
  - bxFinanceUserType (literal value of AnyWealthAdvisor... this is used in the app and by PF provisioning to PD.)
* The workforce's Marketing app connection to PingFed needs the following attributes,
  - subject
  - FirstName
  - LastName
  - Email
  - bxFinanceUserType (literal value of AnyMarketing... this is used in the app and by PF provisioning to PD.)
* Mailtrap
  - This is used as the SMTP server (PingFed notification publisher) and inbox for mail that PingFed sends. This is currenty only used for userName recovery.
  - Accounts are free. @see https://mailtrap.io/how-it-works
  
## Basic User Testing 
* Follow the demo instructions in High Spot @see https://pingidentity.highspot.com/items/5f5a3c98a2e3a97e65700e3e?lfrm=srp.4

# Postman Collections
* Get Token (https://www.getpostman.com/collections/b609316f6c96f8a9fd8a)
* PingDataGov Test Calls (https://www.getpostman.com/collections/d37f14000a04af3fe288)
* PingDirectory Consent APIs (https://www.getpostman.com/collections/d396aa53eaa9fe8e3f82)
