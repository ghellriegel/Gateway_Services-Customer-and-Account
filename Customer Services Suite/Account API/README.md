
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
	- View and download the [Account API YAML](account%20API%202020-07-16.yaml)

- Build pack 
	- [Download the Account API build pack](Gateway%20Services%20Build%20pack%20-%20account%20API.pdf) to view data definitions of each operation and response status code definitions
	
- Message samples
	- [View message samples for requests and responses](#message-samples)
	
- API Reference	
	- [View API Refence](#Account-API-REST-Reference)	

## Environment information
---
- [Mock environment information - emulated service URL, scenarios mindmap and test data](#mock-environment-information)

- [Test environment information - test scenarios report template and URL endpoints](#test-environment-information)

- [Production environment information - URL endpoint](#production-environment-information)



## Supporting services
---
- Service: Identity and access - view: [How to integrate, OAuth requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

<a name="message-samples"/>
## Message samples
---
* Sample JSON payload messages
	* Requests
	    * [Request with end date](sample%20messages/request_with_end_date.json)
	    * [Request without end date](sample%20messages/request_without_end_date.json)
	    
	* Positive response
	    * [Positive response](sample%20messages/response_positive_response.json)
	  
	* Negative response - http 400
	    * [EV1020 - Token not valid](sample%20messages/response_EV1020_token_is_not_valid.json)
	    * [EV1021 - No token](sample%20messages/response_EV1021_no_token.json)
	    * [EV1022 - Access is not permitted](sample%20messages/response_EV1022_access_is_not_permitted.json)
	    * [EV1100 - Invalid input parameter](sample%20messages/response_EV1100_invalid_input_parameter.json)
	    * [EV1200 - Exceeds the maximum limit](sample%20messages/response_EV1200_exceed_the_max_limit.json)
	    * [EV2234 - IR number failed check digit](sample%20messages/response_EV2234_IR_failed_check_digit.json)
	    * [EV2235 - IR number not found](sample%20messages/response_EV2235_IR_not_found.json)
	    
	* Negative response - http 416
	    * Emulator response payload body: "Requested Range Not Satisfiable"
	    * Production or test environment: body is empty. Http status reasonPhrase: "Requested Range Not Satisfiable"

<a name="Account-API-REST-Reference"/>
## Account API REST Reference

|Service| Verb Action| Description
| -- | -- | -- |
|account | `POST` | This web service is used to get information about an Account|
| list | `POST` | This web service is used to get a list of accounts for a customer ID |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration |

> The `status` service is not available in the mock environemnts. 

<a name="mock-environment-information"/>
## Mock environment information
---
### Mock emulated service URL
| End point|  URL|
|--|--|
 Landing Page | https://mock-cus.ird.digitalpartner.services
 Service Path | https://mock-cus.ird.digitalpartner.services/secure/gateway/account/|

### account mock scenarios mindmap

- [View larger image](images/account%20API%20Emulator%20Mindmap.png)
![Mock Scenarios](images/Account%20API%20Emulator%20Mindmap.png)

### Test data

- The following test data can be tested in our Mock Services environment when submitting requests to the service operations
- This table shows which scenarios (as per their numbers in the mindmap) require specific data to trigger the expected responses.

Scenario ID | Data: IRD number | Http status | Response 
--- | --- | --- | ---


>**NOTE:** The emulated service is not managing authentication. Access delegation/restriction is not emulated and any user has access to the test data.


<a name="test-environment-information"/>
## Test environment information
---
### Test environment URL

#### Test-production Environment (FastSlice HTTP Header required)

* URL Base Path endpoint: https://test5.services.ird.govt.nz:4046/gateway/account/account/

#### Pre-production Environment

* URL Base Path endpoint: https://test6.services.ird.govt.nz:4046/gateway/account/account/

>**NOTE:** These endpoints are subject to change due to environment updates in the future. 

### Test scenarios report template

- [Download Test Scenarios report template](Account%20API-%20Test%20Report%20Template.docx)


<a name="production-environment-information"/>
## Production environment information
---
### Production environment URL

* URL Base Path endpoint: https://services.ird.govt.nz:4046/gateway/account/account/
