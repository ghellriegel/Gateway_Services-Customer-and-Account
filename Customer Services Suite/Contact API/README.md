
![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Contact API 

#### Release version 1.0

## About the Contact API service

Inland Revenue has a suite of digital services available for consumption by our service providers that supports efficient, electronic business interactions with Inland Revenue. 
The Contact Service API described in this build pack document provides current customer information as held by Inland Revenue. 

>**NOTE:** The Contact API Service is only available to Digital Service Providers who use X.509 Digital Certificate used for Mutual TLS on port 4046 and requires OAuth2 or JWT token.

## Key documentation
---
- YAML file
	- View and download the [Contact API YAML](Contact%202020-08-11.yaml)

- Build pack 
	- [Download the Contact API build pack](Build%20pack%20-%20Contact%20API.pdf) to view data definitions of each operation and response status code definitions
	
- API Reference	
	- [View API Refence](#Contact-API-REST-Reference)	

## Environment information
---
- [Mock environment information - emulated service URL, scenarios mindmap](#mock-environment-information)

- [Test environment information - test scenarios report template and URL endpoints](#test-environment-information)

- [Production environment information - URL endpoint](#production-environment-information)

## Supporting services
---- 

Service: Identity and access - view: [How to integrate, OAuth requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

<a name="Contact-API-REST-Reference"></a>
## Contact API REST Reference

|Service| Verb Action| Description
| -- | :--: | -- |
| Contact | `POST` | This web service is used to get information about an Contact|
| list | `POST` | This web service is used to get a list of Contacts for a customer ID |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration |

> The `status` service is not available in the mock environemnts. 

<a name="mock-environment-information"></a>
## Mock environment information
---
### Mock emulated service URL
| End point | URL |
|--|--|
| Landing Page | https://mock-cus.ird.digitalpartner.services |
| Service Path | https://mock-cus.ird.digitalpartner.services/gateway/contact/|

### Contact mock scenarios mindmap

- [View larger image](../images/Contact%20API%20Emulator%20Mindmap.png)
![Mock Scenarios](../images/Contact%20API%20Emulator%20Mindmap.png)

> **NOTE:** The emulated service is not managing authentication. Access delegation/restriction is not emulated and any user has access to the test data.

<a name="test-environment-information"></a>
## Test environment information
---

### Test scenarios report template

- [Download Test Scenarios report template](Contact%20API-%20Test%20Report%20Template.docx)


<a name="production-environment-information"></a>
## Production environment information
---
### Production environment URL

* URL Base Path endpoint: https://services.ird.govt.nz:4046/gateway/contact/
