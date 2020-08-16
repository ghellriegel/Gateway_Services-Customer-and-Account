
![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Income Service 

#### Release version 1.0


## About the service

The Income API described in this build pack document provides a mechanism for external partners to retrieve income data reported to Inland Revenue.

>**NOTE:** The Income API Service is only available to Digital Service Providers who use X.509 Digital Certificate used for Mutual TLS on port 4046 and requires OAuth2 token.


## Key documentation
---
- YAML file
	- View and download the [Income API YAML](Income%20API%202020-07-16.yaml)

- Build pack 
	- [Download the Income API build pack](Gateway%20Services%20Build%20pack%20-%20Income%20API.pdf) to view data definitions of each operation and response status code definitions
	
- Message samples
	- [View message samples for requests and responses](#message-samples)


## Environment information
---
- [Mock environment information - emulated service URL, scenarios mindmap and test data](#mock-environment-information)

- [Test environment information - test scenarios report template and URL endpoints](#test-environment-information)

- [Production environment information - URL endpoint](#production-environment-information)


## Supporting services
---
- Service: Identity and access - view: [How to integrate, OAuth requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)


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


## Mock environment information
---
### Mock emulated service URL
| End point|  URL|
|--|--|
 Landing Page | https://mock-ipr.ird.digitalpartner.services
 Service Path | https://mock-ipr.ird.digitalpartner.services/secure/gateway/income/list |

### Income mock scenarios mindmap

- [View larger image](images/Income%20API%20Emulator%20Mindmap.png)
![Mock Scenarios](images/Income%20API%20Emulator%20Mindmap.png)

### Test data

- The following test data can be tested in our Mock Services environment when submitting requests to the service operations
- This table shows which scenarios (as per their numbers in the mindmap) require specific data to trigger the expected responses.

Scenario ID | Data: IRD number | Http status | Response 
--- | --- | --- | ---


>**NOTE:** The emulated service is not managing authentication. Access delegation/restriction is not emulated and any user has access to the test data.


## Test environment information
---
### Test environment URL

#### Test-production Environment
|Service| Verb Action| Description| URL |
| -- | -- | -- | -- |
|account | `POST` | This web service is used to get information about an Account| https://test5.services.ird.govt.nz:4046/gateway/account/account|
| list | `POST` | This web service is used to get a list of accounts for a customer ID | https://test5.services.ird.govt.nz:4046/gateway/account/list|
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration | https://test5.services.ird.govt.nz:4046/gateway/account/status|


#### Pre-production Environment
|Service| Verb Action| Description| URL |
| -- | -- | -- | -- |
|account | `POST` | This web service is used to get information about an Account| https://test6.services.ird.govt.nz:4046/gateway/account/account|
| list | `POST` | This web service is used to get a list of accounts for a customer ID | https://test6.services.ird.govt.nz:4046/gateway/account/list|
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration | https://test6.services.ird.govt.nz:4046/gateway/account/status|

>**NOTE:** These endpoints are subject to change due to environment updates in the future. 

### Test scenarios report template

- [Download Test Scenarios report template](Income%20API%20Service%20-%20Test%20Report%20Template.docx)


## Production environment information
---
### Production environment URL


|Service| Verb Action| Description| URL |
| -- | -- | -- | -- |
|account | `POST` | This web service is used to get information about an Account| https://services.ird.govt.nz:4046/gateway/account/account|
| list | `POST` | This web service is used to get a list of accounts for a customer ID | https://services.ird.govt.nz:4046/gateway/account/list|
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration | https://services.ird.govt.nz:4046/gateway/account/status|
