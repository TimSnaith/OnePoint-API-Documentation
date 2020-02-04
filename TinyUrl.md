## TinyUrl
The TinyUrl API's allow you to generate tiny URL's for your SMS messages.

### Register
Register a URL in return for a tiny URL.
```
URL: https://api.1pt.mobi/gateway/api/TinyUrl/Register
Method: POST
{
  "FullUrl": "sample string 1"
}
```
#### Returns
```
{ "The tiny url" }
```
#### Statuses
* 200 - Success
* 400 - Invalid Session. Please ensure you Login first
* 400 - There was a problem registering the tiny url

### RegisterList
Register a list of URL's in return for a list of tiny URL's
```
URL: https://api.1pt.mobi/gateway/api/TinyUrl/RegisterList
Method: POST
{
  "UrlList": [
    {
      "FullUrl": "sample string 1"
    },
    {
      "FullUrl": "sample string 1"
    }
  ]
}
```
#### Returns
```
{
  "UrlList": [ "tinyUrl1", "tinyUrl2" ]
}
```
#### Statuses
* 200 - Success
* 400 - Invalid Session. Please ensure you Login first
* 400 - There was a problem registering the tiny url
