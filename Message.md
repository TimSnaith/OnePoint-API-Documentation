## Message
The Message API's allow you to send SMS messages acrosas a global network.

### Lookup
```
URL: https://api.1pt.mobi/gateway/api/Message/Lookup?number={number}
Method: GET
```
#### Returns
```
{
  "Number": "sample string 1",
  "Carrier": "sample string 2",
  "Message": "sample string 3",
  "Reachable": true,
  "Status": "sample string 5",
  "NumberType": "sample string 6"
}
```
#### Statuses
* 200 - Success
* 400 - Invalid Session. Please ensure you Login first
* 400 - There was a problem with the Lookup. Please check your request and try again

### Send
```
URL: https://api.1pt.mobi/gateway/api/Message/Send
Method: POST
{
  "Source": "sample string 1",
  "Destination": "sample string 2",
  "Message": "sample string 3",
  "Reply": true,
  "When": "2020-02-04T11:47:33.645773+00:00"
}
```
#### Returns
```
nothing
```
#### Statuses
* 200 - Success
* 400 - Invalid Session. Please ensure you Login first
* 400 - The destination number is invalid
* 400 - The destination and source cannot be the same
* 400 - The message length must be greater than zero
* 400 - There was a problem sending the message. Please contact OnePoint Global Support