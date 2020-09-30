
![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Address API 

#### Release version 1.0

## About the Address API service

Inland Revenue has a suite of digital services available for consumption by our service providers that supports efficient, electronic business interactions with Inland Revenue. 
The Address Service API described in this build pack document provides current customer information as held by Inland Revenue. 

>**NOTE:** The Address API Service is only available to Digital Service Providers who use X.509 Digital Certificate used for Mutual TLS on port 4046 and requires OAuth2 or JWT token.

## Key documentation
---
- YAML file
	- View and download the [Address API YAML](Address%202020-09-28.yaml)

- Build pack 
	- [Download the Address API build pack](Build%20pack%20-%20Address%20API.pdf) to view data definitions of each operation and response status code definitions
	
- API Reference	
	- [View API Refence](#Address-API-REST-Reference)	

## Environment information
---
- [Mock environment information - emulated service URL, scenarios mindmap and test data](#mock-environment-information)

- [URL Endpoints and API reference ](#Address-API-REST-Reference)

- [Test environment information - Report Template](#test-environment-information)

## Supporting services
---- 

Service: Identity and access - view: [How to integrate, OAuth & JWT requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

<a name="Address-API-REST-Reference"></a>
## Address URL Endpoints and API Reference

| Environment | Scheme Authority |  
| --- | --- |
| Mock (DPS)| `https://mock-cus.ird.digitalpartner.services`|
| Production (PROD) | `https://services.ird.govt.nz:4046`|

#### Address API - `*{Scheme Authority}*/gateway/address/{Service}`
| Service | HTTP request types | Description |  
| -- | :--: | -- | 
| address | `DELETE` | This web service is used to remove an address | 
| address | `PUT` | This web service is used to update an address | 
| address | `POST` | This web service is used to add an address | 
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration |

> The `status` service is not available in the mock environemnts. 

<a name="mock-environment-information"></a>
## Mock environment information
---
### Mock emulated service URL

- Landing Page https://mock-cus.ird.digitalpartner.services 

### Address mock scenarios mindmap

- [View larger image](../images/Address%20API%20Mock%20Service.png)
![Mock Scenarios](../images/Address%20API%20Mock%20Service.png)

<a name="test-environment-information"></a>
### Test scenarios report template

- [Download Test Scenarios report template](Address%20API-%20Test%20Report%20Template.docx) - *Coming Soon*








