
![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Name API 

#### Release version 1.0 

## About the Name API

The name API enables the creating, updating, and deleting of the customer’s names. It is one of seven APIs that together make up the customer services suite. 

>**NOTE:** The Name API is only available to Digital Service Providers who use X.509 Digital Certificate used for Mutual TLS on port 4046 and requires OAuth2 or JWT token.

## Key documentation

* View and download the [Name API YAML](Name%202020-09-30.yaml)
* [Download the Name API build pack](Build%20pack%20-%20Name%20API.pdf) to view data definitions of each operation and response status code definitions
* [View API Reference and URL Endpoints](#Name-API-REST-Reference)	

## Environment information

* [Mock environment information - emulated service URL, scenarios mindmap and test data](#mock-environment-information)

## Supporting services
* Service: Identity and access - view: [How to integrate, M2M JWT, OAuth requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

<a name="Name-API-REST-Reference"></a>
## Name API REST Reference

| Environment | Scheme Authority | Mutual TLS (mTLS) authentication |
| --- | --- | :---: |
| Mock (DPS)| `https://mock-cus.ird.digitalpartner.services`| no |
| Production (PROD) | `https://services.ird.govt.nz:4046`| yes |

#### Name API - `{Scheme Authority}/gateway/name/{Service}`
| Service | HTTP request types | Description | 
| :--: | :--: | -- |
| name | `POST` | Adds a name of a given type (preferred/trading) to the customer data set |
| name | `PUT` | Updates the details of an existing name in the customer data set |
| name | `DELETE` | Deletes a given name from the customer data set |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should *only* be used to validate the service and credential configuration | 

> The `status` service might not be available in the mock environemnt.

---

<a name="mock-environment-information"></a>
## Mock environment information

### Name mock scenarios mindmap

[View larger image](images/Name%20API%20Emulator%20Mindmap.png)
![Mock Scenarios](images/Name%20API%20Emulator%20Mindmap.png)

<a name="mock-environment-information"></a>
## Mock environment information

### Mock emulated service URL
* Landing Page https://mock-cus.ird.digitalpartner.services 

### Name API mock scenarios mindmap

[View larger image](../images/Name%20API%20Mock%20Service.png)
![Mock Scenarios](../images/Name%20API%20Mock%20Service.png)

### Mock environment authentication
* Consumers of this mock service must be authenticated.
* Access delegation/restriction is not emulated, and any authenticated user has access to the test data.
* Authentication is provided using one of two methods:
 1. OAuth
	* OAuth token issued by the mock OAuth service. Any valid token issued by the mock OAuth service can be used to access this service.
	* Please consult the [mock OAuth service documentation](https://mock-oauth.ird.digitalpartner.services/) for further details about the authentication process.
	* The OAuth token should be provided in the 'Authorization' request header as follows:
	```
	Authorization: Bearer {OAuthAccessToken}
	```
 2. JWT
	* Alternatively a self-issued JWT may be used to access the service.
	* Please consult the build pack for information on the token structure.
	* The mock service does not validate the following JWT attributes:
		* "sub" field
		* "iss" field
		* token signature
	* The JWT should be provided in the 'Authorization' request header as follows (note the 'Bearer' prefix is omitted):
	```
	Authorization: {JWT}
	```


### Test scenarios report template

* [Download Test Scenarios report template](Name%20API-%20Test%20Report%20Template.docx) - *Coming Soon*

