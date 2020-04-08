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

## Administrator Access - SaaS Services
* Access [P14E-PID Administration] (https://admin.pingone.com/web-portal/login)
  - Use your own creds to login
* Access [MailTrap] (https://mailtrap.io/)
  - rlyle+bxfinance@pingidentity.com / 2FederateM0re

## Basic User Testing 
* Access [Delegated Administration] (https://sso.anycompany.co/delegator/)
  - useradmin / 2FederateM0re
* Access [Simple SP Connection] (https://sso.anycompany.co/idp/startSSO.ping?PartnerSpId=Dummy-SAML)
  - user.0 / 2FederateM0re
* Test out [PDG Pass-Through] (https://pingdatagovernance:3443/anything)
  - user.0 / 2FederateM0re
  - Obtain AT from PingFederate (https://sso.anycompany.co/as/authorization.oauth2?response_type=token&client_id=PingToken)
* Test out [PD Consents]  (https://pingdirectory:2443/consent/v1/consents?definition=test-consent&subject=user.1)
  - Obtain AT from PingFederate or use Basic Authorization
  - Obtain AT from PingFederate (https://sso.anycompany.co/as/authorization.oauth2?response_type=token&client_id=PingToken&scope=urn:pingdirectory:consent)




  


