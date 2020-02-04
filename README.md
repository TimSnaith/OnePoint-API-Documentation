# OnePoint API
Welcome to the OnePoint API Documentation. This is for general use of OnePoint Global's Open API available on the end point https://api.1pt.mobi/gateway, which contains a limited copy of the documentation.

The API is offers RESTful access to a set of capabilities that allow access to a global SMS network.

## Working with OnePoint's API
OnePoint's API requires authentication to be achieved to gain a session that is then used for subsequent requests to the API. It is then recommended that you discard the session in a propper manner.

### Authentication
Authentication is done using the following API:
```
https://api.1pt.mobi/gateway/api/Account/Login
```
