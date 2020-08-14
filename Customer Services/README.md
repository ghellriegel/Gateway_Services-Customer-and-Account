
![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# Customer Services 
#### Release version 1.0 

## About the Customer Services
The 'Customer Services’ is suite of APIs designed to be used together — Account, Address, Bank Account, Contact, Customer Service, Name and Period. It is 
important to understand the dependencies between these when deciding which ones to implement, how to correctly sequence their adoption, how authorisation rules 
impact access, and how to use them in general. 

### [Account Service API](Service%20-%20Account)
This Read-only API will be used by approved organisations to retrieve account information from Inland Revenue.

### [Address Service API](Service%20-%20Address)
The Address API provides current information about the addresses held by Inland Revenue.

### [Bank Account API](Service%20-%20Account) 
The Bank Account API is used to update the bank account number as held by Inland Revenue.

### [Contact API](Service%20-%20Contact) 
The Contact API provides current information about the addresses held by Inland Revenue.

### [Customer Service API](Service%20-%20Customer)
The Customer Service API provides current customer information as held by Inland Revenue. 

### [Customer Name API](Service%20-%20Name)
The Name API provides current customer information as held by Inland Revenue. 

### [Customer Period API](Service%20-%20Period)
The Read-only Period API provides current customer information as held by Inland Revenue. 


## Customer Services REST API reference

You'll need to use different APIs depending on the service that your app provides. Use the following tables to see which APIs are useful for different kinds of tasks.

#### Account API - `/gateway/account/{Service}`
| Service | Method | Description | 
| :--: | :--: | -- |
| account | `POST` | This web service is used to get information about an Account | 
| list | `POST` | This web service is used to get a list of accounts for a customer ID | 
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration | 

#### Address API - `/gateway/address{Service}`
| Service | Method | Description | 
| -- | :--: | -- |
| address | `DELETE` | This web service is used to remove an address | 
| address | `PUT` | This web service is used to update an address | 
| address | `POST` | This web service is used to add an address |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration |  

#### Contact API - `/gateway/contact/{Service}`
| Service | Method | Description | 
| :--: | :--: | -- |
| contact | `POST` | This web service is used to add a contact | 
| contact | `PUT` | This web service is used to update a contact | 
| contact | `DELETE` | This web service is used to delete a contact | 
| phone | `POST` | This web service is used to add a phone number to an existing contac | 
| phone | `PUT` | This web service is used to update a phone number on an existing contact | 
| phone | `DELETE` | This web service is used to update a phone number on an existing contact | 
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration | 

#### Customer API - `/gateway/customer/{Service}`
| Service | Method | Description | 
| :--: | :--: | -- |
| customer | `POST` | This web service is used to get information about a Customer |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration | 


#### Name API - `/gateway/name/{Service}`
| Service | Method | Description | 
| :--: | :--: | -- |
| name | `POST` | This web service creates names in START |
| name | `PUT` | This web service updates names in START |
| name | `DELETE` | This web service deletes names in START |
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration | 

#### Period API - `/gateway/period/{Service}`
| Service | Method | Description | 
| :--: | :--: | -- |
| list | `POST` | This web service is used to get a list of period for a given Account ID.| 
| status | `GET` | This web service sends a 200 HTTP response with a message body of "OK". This is preferred over service "ping" functionality as this should validate the service and credential configuration | 
