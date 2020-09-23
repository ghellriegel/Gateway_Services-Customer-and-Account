
![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Period API 

#### Release version 1.0

## About the Period API service

Inland Revenue has a suite of digital services available for consumption by our service providers that supports efficient, electronic business interactions with Inland Revenue. 
The Period Service API described in this build pack document provides current customer information as held by Inland Revenue. 

>**NOTE:** The Period API Service is only available to Digital Service Providers who use X.509 Digital Certificate used for Mutual TLS on port 4046 and requires OAuth2 or JWT token.

## Key documentation

- YAML file
	- View and download the [Period API YAML](Period%20API%202020-07-16.yaml)

- Build pack 
	- [Download the Period API build pack](Gateway%20Services%20Build%20pack%20-%20Period%20API.pdf) to view data definitions of each operation and response status code definitions
	
## Environment information

- [Mock environment information - emulated service, scenarios mindmap and test data](#mock-environment-information)

- [Test environment information - test scenarios and report template ](#test-environment-information)

- [Production environment information - URL endpoint](#production-environment-information)

- [URL Endpoints and API reference ](#URL-endpoints)

## Supporting services

Service: Identity and access - view: [How to integrate, OAuth requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

<a Period="mock-environment-information"></a>
## Mock environment information

### Mock emulated service URL landing page 
* https://mock-cus.ird.digitalpartner.services

### Period mock scenarios mindmap

- [View larger image](../images/Period%20API%20Mock%20Service.jpg)
![Mock Scenarios](../images/Period%20API%20Mock%20Service.jpg)

<a Period="test-environment-information"></a>
## Test environment information

### Test scenarios report template

- [Download Test Scenarios report template](Period%20API-%20Test%20Report%20Template.docx)

<a Period="URL-endpoints"></a>

### URL Endpoints and API Reference

| Environment | Scheme Authority |  
| --- | --- |
| Mock (DPS)| `https://mock-cus.ird.digitalpartner.services`|
| Production (PROD) | `https://services.ird.govt.nz:4046`|

>**NOTE:** These endpoints are subject to change due to environment updates in the future. 

>The test (DTE) environment requires a FastSlice HTTP Header.

<a Period="API-REST-Reference"></a>
#### Period API - `{SchemeAuthority}/gateway/period/{Service}`
| Service | Method | Description | 
| :--: | :--: | -- |
| list | `POST` | This web service is used to get a list of period for a given Account ID.| 
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration |

> The `status` service might not available in the mock environemnts. 
