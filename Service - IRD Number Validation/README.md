![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# IRD Number Validation Service API
---
#### Release version 1.0
The IRD Number Validation Service enables the consumer of the service to receive confirmation that an IRD number provided is a correct match (or not) for a customer based on the identity attributes provided.

This API can be used by approved Digital Service Providers (DSPs) to validate customer information with Inland Revenue.

>**NOTE:** The IRD Number Validation Service is only available to approved Digital Service Providers who use a X.509 Digital Certificate for Mutual TLS on port 4046.  

This service supports the following message type: 
 
* **READ:** Retrieves match from Inland Revenue. Requires an IRD number and other information about the customer. 

## Key Documentation:

- YAML file:
	- View and download the [Customer%20Service%202020-03-10](Customer%20Service%202020-03-10.yaml)

- IRD Number Validation build pack
	- [Download the build pack](Build%20pack%20-%20IRD%20Number%20Validation%20Service.pdf) to view data definitions of each operation and response status code definitions
	
* Message Samples
	* [View message samples for requests and positive responses](#Message-Samples)

## Environment Information
- [Mock Environment Information - Emulated Services, MindMap and Test data](#-mock-environment-information)

- [Test Environment Information - Test Scenarios Report Template and URL Endpoints](#-test-environment-information)

- [Production Environment Information - URL Endpoint](#-prod-environment-information)

## Message samples:
-----------------

- Simulating IRD Number validation  Operations:
    - Request and Response Samples
        -  Sample Requests
            - [Request with FormattedName, FormattedAddress and NZBN](sample%20messages/formatted_name_formatted_Address_NZBN.json)
            - [Request with Name and Address](sample%20messages/name_and_address.json)
        -   Positive Responses (http 200)
            - [Match](sample%20messages/match-response.json)
            - [No match](sample%20messages/no_match_response.json)
        -   Negative Response (http 400)
            - [Error IR002 - The NZBN supplied does not match the customer](sample%20messages/nzbn_does_not_match.json)

## Mock Environment Information
---
### Mock Emulated service URL
| End point|  URL|
|--|--|
| Mock | https://mock-irv.ird.digitalpartner.services/secure/gateway/customer-service/validateIRD |

### Mock Scenarios MindMap

- [View larger image](images/IRD%20Number%20Validation%20API.png)
![Mock Scenarios](images/IRD%20Number%20Validation%20API.png)

### Test Data
   - The following test data can be tested in our Mock Services environment when submitting requests to the service operations
   - This table shows which scenarios (as per their numbers in the mindmap) require specific data to trigger the expected responses.

      Scenario ID | Data | Response 
    	--- | --- | ---
    	MOCK-01 | Customer IRD (*identifier*): 123344677 | HTTP Response Code - 200
    	MOCK-02 | Customer IRD (*identifier*): 123344952 | HTTP Response Code - 200
    	MOCK-20 | Customer IRD (*identifier*): 123345002 | HTTP Response Code - 400
    	MOCK-30 | Customer IRD (*identifier*): 123456789 | HTTP Response Code - 400
    	

## Test environment information
---
### Test environment URL
| End point|  URL|
|--|--|
- Testing : https://test3.services.ird.govt.nz:4046/Gateway/customer-service/validateIRD
- Pre-Production : https://test5.services.ird.govt.nz:4046/Gateway/customer-service/validateIRD  

>**NOTE:** These endpoints are subject to change due to environment updates in the future. 

### Test scenarios report template

- [Download Test Scenarios report template](IRD%20Validation%20Service%20-%20Test%20Report%20Template.docx)

## Prod environment information
---
### Prod environment URL
| End point|  URL|
|--|--|
- Production : https://services.ird.govt.nz:4046/Gateway/customer-service/validateIRD
