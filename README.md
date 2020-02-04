# OnePoint API
Welcome to the OnePoint API Documentation. This is for general use of OnePoint Global's Open API available on the end point https://api.1pt.mobi/gateway, which contains a limited copy of the documentation.

The API is offers RESTful access to a set of capabilities that allow access to a global SMS network.

## Working with OnePoint's API
OnePoint's API requires authentication to be achieved to gain a session that is then used for subsequent requests to the API. It is then recommended that you discard the session in a propper manner.

### Authentication
Authentication is done using the following API:
```
URL: https://api.1pt.mobi/gateway/api/Account/Login
Method: POST
Content: { "Username":"username", "Password":"password" }
```
All API's will return either a success status (200) or a failure status which can vary depedning on the error. If the above API is successful then it will return a Session ID in the following format:
```
{ "SessionId": "ABCCDEFG" }
```
The Session ID must be used in subsequent API calls by placing it in the header with the name `SessionId`. For example, to send an SMS the following API would be used:
```
URL: https://api.1pt.mobi/gateway/api/Send
Header:
SessionId:"ABCDEFG"
Method: POST
Content:
{
  "Source": "sample string 1",
  "Destination": "sample string 2",
  "Message": "sample string 3",
  "Reply": true,
  "When": "2020-02-04T11:47:33.645773+00:00"
}
```
When a session is no longer required then the following API will remove it:
```
URL: https://api.1pt.mobi/gateway/api/Logout
Header:
SessionId:"ABCDEFG"
Method: POST
```

### Statuses
Every API will return a status which can be one of the following:
* 200 - Success
* 400 - Bad request. the HTTP message will vary depedning on the type of problem.

### API's
The API's are split into the following:
* [Account](Account.md)
* [Keyword](Keyword.md)
* [TinyUrl](TinyUrl.md)
* [Message](Message.md)
* [Survey](Survey.md)
* [Recipient](Recipient.md)

