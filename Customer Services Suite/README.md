
![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# Customer Services Suite
#### Release version 1.0 

## About the Customer Services Suite
The 'Customer Services Suite’ is collection of APIs designed to be used together — Account, Address, Bank Account, Contact, Customer Service, Name and Period. It is 
important to understand the dependencies between these when deciding which ones to implement, how to correctly sequence their adoption, how authorisation rules 
impact access, and how to use them in general. 

### [Account API](Account%20API) _(Read-only)_
This API will be used by approved organisations to retrieve account information from Inland Revenue.

### [Address API](Address%20API)
The Address API provides current information about the addresses held by Inland Revenue.

### [Bank Account API](Bank%20Account%20API) 
The Bank Account API is used to update the bank account number as held by Inland Revenue.

### [Contact API](Contact%20API) 
The Contact API provides current information about the addresses held by Inland Revenue.

### [Customer API](Customer%20API) _(Read-only)_
The Customer API provides current customer information as held by Inland Revenue. 

### [Name API](Name%20API)
The Name API provides current customer information as held by Inland Revenue. 

### [Period API](Period%20API) _(Read-only)_
The Period API provides current customer information as held by Inland Revenue. 


## Customer Services Suite REST API reference

You'll need to use different APIs depending on the service that your app provides. Use the following tables to see which APIs are useful for different kinds of tasks.

#### Account API - `/gateway/account/{Service}`
| Service | HTTP request types | Description | 
| :--: | :--: | -- |
| account | `POST` | This web service is used to get information about an Account | 
| list | `POST` | This web service is used to get a list of accounts for a customer ID | 

#### Address API - `/gateway/address{Service}`
| Service | HTTP request types | Description |
| -- | :--: | -- | 
| address | `DELETE` | This web service is used to remove an address | 
| address | `PUT` | This web service is used to update an address | 
| address | `POST` | This web service is used to add an address | 

#### Bank API - `/gateway/bank{Service}`
| Service | HTTP request types | Description | 
| -- | :--: | -- | 
| bank |  `DELETE` | This web service is used to remove a bank account from an account  |
| bank |  `POST` | This web service is used to add a bank account to an account  |

#### Contact API - `/gateway/contact/{Service}`
| Service | HTTP request types | Description | 
| :--: | :--: | -- |
| contact | `POST` | This web service is used to add a contact | 
| contact | `PUT` | This web service is used to update a contact | 
| contact | `DELETE` | This web service is used to delete a contact | 
| phone | `POST` | This web service is used to add a phone number to an existing contact | 
| phone | `PUT` | This web service is used to update a phone number on an existing contact | 
| phone | `DELETE` | This web service is used to update a phone number on an existing contact | 

#### Customer API - `/gateway/customer/{Service}`
| Service | HTTP request types | Description | 
| :--: | :--: | -- |
| customer | `POST` | This web service is used to get information about a Customer |


#### Name API - `/gateway/name/{Service}`
| Service | HTTP request types | Description | 
| :--: | :--: | -- |
| name | `POST` | This web service creates names in START |
| name | `PUT` | This web service updates names in START |
| name | `DELETE` | This web service deletes names in START |

#### Period API - `/gateway/period/{Service}`
| Service | Method | Description | 
| :--: | :--: | -- |
| list | `POST` | This web service is used to get a list of period for a given Account ID.| 


#### Common across all APis - `/gateway/{api}/status`
| Service | Method | Description | 
| :--: | :--: | -- |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration | 