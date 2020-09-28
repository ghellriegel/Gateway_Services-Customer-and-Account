
![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Account API 

#### Release version 1.0

## About the Account API service

Inland Revenue has a suite of digital services available for consumption by our service providers that supports efficient, electronic business interactions with Inland Revenue. 
The Account Service API described in this build pack document provides current customer information as held by Inland Revenue. 

>**NOTE:** The Account API Service is only available to Digital Service Providers who use X.509 Digital Certificate used for Mutual TLS on port 4046 and requires OAuth2 or JWT token.

## Key documentation
---
- YAML file
	- View and download the [Account API YAML](Account%202020-09-28.yaml)

- Build pack 
	- [Download the Account API build pack](Build%20pack%20-%20Account%20Service%20API.pdf) to view data definitions of each operation and response status code definitions

- API Reference	
	- [View API Refence](#Account-API-REST-Reference)

## Environment information
---
- [Mock environment information - emulated service URL, scenarios mindmap and test data](#mock-environment-information)


- [Production environment information - URL endpoint](#production-environment-information)

## Supporting services

Service: Identity and access - view: [How to integrate, OAuth requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

<a name="Account-API-REST-Reference"></a>
## Account API REST Reference

|Service| Verb Action| Description |
| -- | :--: | -- |
|account | `POST` | This web service is used to get information about an Account|
| list | `POST` | This web service is used to get a list of accounts for a customer ID |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration |

> The `status` service is not available in the mock environemnts. 

<a name="mock-environment-information"></a>
## Mock environment information

### Mock emulated service URL
| End point|  URL|
|--|--|
 Landing Page | https://mock-cus.ird.digitalpartner.services
 Service Path | https://mock-cus.ird.digitalpartner.services/secure/gateway/account/|

### Account mock scenarios mindmap

- [View larger image](../images/Account%20API%20Mock%20Service.png)
![Mock Scenarios](../images/Account%20API%20Mock%20Service.png)

> **NOTE:** The emulated service is not managing authentication. Access delegation/restriction is not emulated and any user has access to the test data.


<a name="test-environment-information"></a>
## Test environment information

### Test scenarios report template

- [Download Test Scenarios report template](Account%20API-%20Test%20Report%20Template.docx)


<a name="production-environment-information"></a>
## Production environment information

### Production environment URL

* URL Base Path endpoint: https://services.ird.govt.nz:4046/gateway/account/account/
