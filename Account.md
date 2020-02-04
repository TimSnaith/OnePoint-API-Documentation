## Account API's
The Account API's are made up of the following:

### Login
Before any other API is used you will need a Session Id. This API requests one.
```
URL: https://api.1pt.mobi/gateway/api/Account/Login
Method: POST
Content: { "Username":"username", "Password":"password" }
```
#### Parameters
Name | Description
---- | -----------
Username | The account's user name. Cannot be blank.
Password | The account's password.

#### Returns
```
{ "SessionId": "ABCCDEFG" }
```
The `SessionId` must be used in subsquent calls by placing it in the header a value with the name `SessionId`.
#### Statuses
Status | Description
------ | -----------
200 | Success
400 | The username and/or password is incorrect

### LoginWithUid
Before any other API is used you will need a Session Id. This API requests one using the User's ID (available through the account 
properties in your account).
```
URL: https://api.1pt.mobi/gateway/api/Account/LoginWithUid
Method: POST
Content: "Uid" }
```
#### Parameters
Name | Description
---- | -----------
Uid | The User Id available by logging into your account and checking your account details.
#### Returns
```
{ "SessionId": "ABCCDEFG" }
```
The `SessionId` must be used in subsquent calls by placing it in the header a value with the name `SessionId`.
#### Statuses
Status | Description
------ | -----------
200 | Success
400 | The uid is invalid

### Logout
To discard a Session Id after all other API's have been used you need to logout.
```
URL: https://api.1pt.mobi/gateway/api/Logout
Header:
SessionId:"ABCDEFG"
Method: POST
```
#### Returns
nothing
#### Statuses
Status | Description
------ | -----------
200 | Success
400 | Invalid Session. Please ensure you Login first

