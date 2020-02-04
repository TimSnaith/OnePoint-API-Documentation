## Message
The Message API's allow you to send SMS messages acrosas a global network.

### Lookup
Lookup a number on the network to see whether it is reachable and whether it is a mobile number.
```
URL: https://api.1pt.mobi/gateway/api/Message/Lookup?number={number}
Method: GET
```
#### Parameters
Name | Description
---- | -----------
number | The number to lookup
#### Returns
```
{
  "Number": "01234567890",
  "Carrier": "EE",
  "Message": "Success Message",
  "Reachable": true,
  "Status": "Success",
  "NumberType": "Mobile"
}
```
#### Return Parameters
Name | Description
---- | -----------
Number | The number that was looked up
Carrier | The name of the carrier. This can be any valid string or the work `Unknown`
Message | A status message which vary depending on the success of the lookup and the carrier involved.
Reachable | A boolean value indicating whether the number is reachable.
Status | A string indicating the result of the lookup. Either `Success` or `Failure`
NumberType | A string indicating the type of number - `Mobile`, `Landline` or `Unknown`

#### Statuses
* 200 - Success
* 400 - Invalid Session. Please ensure you Login first
* 400 - There was a problem with the Lookup. Please check your request and try again

### Send
Send an SMS message anywhere in the world.
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
#### Parameters
Name | Description
---- | -----------
Source | The source of the message. This can be a short cod, a long number or a branded valuye up to 11 characters long.
Destination | The destination of the message. this must be a the full number prefixed with the country code and no leading zeroes.
Message | The text message to send. This can be up to 2000 characters long.
Reply | A boolean value indicating whether the message can be replied to or not. If this is true then the destination may be replaced 
depending on desintation value and the route the message has to take to get to its destination.
When | A date and time indicating when the message should be sent. This is 

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