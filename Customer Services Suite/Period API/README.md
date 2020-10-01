
![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Period API 

#### Release version 1.0

## About the Period API service

Inland Revenue has a suite of digital services available for consumption by our service providers that supports efficient, electronic business interactions with Inland Revenue. 
The Period Service API described in this build pack document provides current customer information as held by Inland Revenue. 

>**NOTE:** The Period API Service is only available to Digital Service Providers who use X.509 Digital Certificate used for Mutual TLS on port 4046 and requires OAuth2 or JWT token.

## Key documentation

* View and download the [Period API YAML](Period%202020-09-30.yaml)
* [Download the Period API build pack](Build%20pack%20-%20Period%20API.pdf) to view data definitions of each operation and response status code definitions
	
## Environment information

* [Mock environment information - emulated service, scenarios mindmap and test data](#mock-environment-information)
* [URL Endpoints and API reference](#URL-endpoints)

## Supporting services

Service: Identity and access - view: [How to integrate, OAuth requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

---

### URL Endpoints and API Reference

| Environment | Scheme Authority | mutual TLS |
| --- | --- | :---: |
| Mock (DPS)| `https://mock-cus.ird.digitalpartner.services`| no |
| Production (PROD) | `https://services.ird.govt.nz:4046`| yes |

<a Period="API-REST-Reference"></a>
#### Period API - `{Scheme Authority}/gateway/period/{Service}`
| Service | HTTP request types | Description | 
| :--: | :--: | -- |
| list | `POST` | Returns the information of periods for an identified customer account | 
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should *only* be used to validate the service and credential configuration | 

> The `status` service might not available in the mock environemnts. 


<a Period="mock-environment-information"></a>
## Mock environment information

### Mock emulated service URL landing page 
* https://mock-cus.ird.digitalpartner.services

### Period mock scenarios mindmap

[View larger image](../images/Period%20API%20Mock%20Service.jpg)
![Mock Scenarios](../images/Period%20API%20Mock%20Service.jpg)

### Test scenarios report template

* [Download Test Scenarios report template](Period%20API-%20Test%20Report%20Template.docx) - *Coming Soon*

