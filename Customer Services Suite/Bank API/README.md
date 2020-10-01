
![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Bank API 

#### Release version 1.0

## About the Bank API 

The bank account API enables the creating and deleting of the refund bank account for an identified customer’s account. It is one of seven APIs that together make up the customer services suite.

>**NOTE:** The Bank API is only available to Digital Service Providers who use X.509 Digital Certificate used for Mutual TLS on port 4046 and requires OAuth2 or JWT token.

## Key documentation
* View and download the [Bank API YAML](Bank%202020-09-28.yaml)
* [Download the Bank API build pack](Build%20pack%20-%20Bank%20Account%20API.pdf) to view data definitions of each operation and response status code definitions
* [View API Reference and URL endpoints](#Bank-API-REST-Reference)	

## Environment information
* [Mock environment information - emulated service URL, scenarios mindmap and test data](#mock-environment-information)

## Supporting services
* Service: Identity and access - view: [How to integrate, M2M JWT, OAuth requests and responses message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

<a name="Contact-API-REST-Reference"></a>
## Bank API REST Reference and URL endpoints

| Environment | Scheme Authority | Mutual TLS (mTLS) authentication |
| --- | --- | :---: |
| Mock (DPS)| `https://mock-cus.ird.digitalpartner.services`| no |
| Production (PROD) | `https://services.ird.govt.nz:4046`| yes |

#### Bank API - `{Scheme Authority}/gateway/bank/{Service}`
| Service | HTTP request types | Description | 
| -- | :--: | -- | 
| bank |  `DELETE` | Deletes the refund bank account from the identified customer account |
| bank |  `POST` | Adds a refund bank account to the identified customer account if there is not already a refund bank account on the customer account<br/>Or<br/>Replaces an existing refund bank account on the identified customer account  |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should *only* be used to validate the service and credential configuration | 

> The `status` service might not be available in the mock environemnt.

<a name="mock-environment-information"></a>
## Mock environment information
---

### Mock emulated service URL
* Landing Page https://mock-cus.ird.digitalpartner.services 

### Bank mock scenarios mindmap

[View larger image](../images/Bank%20API%20Mock%20Service.png)
![Mock Scenarios](../images/Bank%20API%20Mock%20Service.png)

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
        * Please consult the build pac for information on the token structure.
        * The mock service does not validate the following JWT attributes:
            * "sub" field
            * "iss" field
            * token signature
        * The JWT should be provided in the 'Authorization' request header as follows (note the 'Bearer' prefix is omitted):
        ```
        Authorization: {JWT}
        ```
		
### Test scenarios report template

- [Download Test Scenarios report template](Bank%20API-%20Test%20Report%20Template.docx) - *Coming Soon*



