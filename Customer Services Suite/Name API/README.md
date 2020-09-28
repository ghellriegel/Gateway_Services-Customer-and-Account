
![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Name API 

#### Release version 1.0 - Coming Soon. 

## About the Name API service

Inland Revenue has a suite of digital services available for consumption by our service providers that supports efficient, electronic business interactions with Inland Revenue. 
The Name Service API described in this build pack document provides current customer information as held by Inland Revenue. 

>**NOTE:** The Name API Service is only available to Digital Service Providers who use X.509 Digital Certificate used for Mutual TLS on port 4046 and requires OAuth2 or JWT token.

## Key documentation
---
- YAML file
	- View and download the [Name API YAML](Name%202020-09-28.yaml)

- Build pack 
	- [Download the Name API build pack](Build%20pack%20-%20Name%20API.pdf) to view data definitions of each operation and response status code definitions
	
- API Reference	
	- [View API Refence](#Name-API-REST-Reference)	

## Environment information
---
- [Mock environment information - emulated service URL, scenarios mindmap and test data](#mock-environment-information)

- [Test environment information - test scenarios report template and URL endpoints](#test-environment-information)

- [Production environment information - URL endpoint](#production-environment-information)

## Supporting services
---
Service: Identity and access - view: [How to integrate, OAuth requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

<a name="Name-API-REST-Reference"></a>
## Name API REST Reference

|Service| Verb Action| Description|
| -- | -- | -- |
| Name | `POST` | This web service is used to get information about an Name|
| list | `POST` | This web service is used to get a list of Names for a customer ID |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration |

> The `status` service is not available in the mock environemnts. 

<a name="mock-environment-information"></a>
## Mock environment information
---
### Mock emulated service URL
| End point | URL|
| -- | -- |
| Landing Page | https://mock-cus.ird.digitalpartner.services | 
| Service Path | https://mock-cus.ird.digitalpartner.services/gateway/name/|

### Name mock scenarios mindmap

- [View larger image](images/Name%20API%20Emulator%20Mindmap.png)
![Mock Scenarios](images/Name%20API%20Emulator%20Mindmap.png)

> **NOTE:** The emulated service is not managing authentication. Access delegation/restriction is not emulated and any user has access to the test data.

<a name="test-environment-information"></a>
## Test environment information
---
### Test scenarios report template

- [Download Test Scenarios report template](Name%20API-%20Test%20Report%20Template.docx)

<a name="production-environment-information"></a>
## Production environment information
---
### Production environment URL

* URL Base Path endpoint: https://services.ird.govt.nz:4046/gateway/name/
