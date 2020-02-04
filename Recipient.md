## Recipient
The Recipient API's allow you to add recipients into a recipient list.

### Add
Add recipients to a recipient list.
```
URL: https://api.1pt.mobi/gateway/api/Recipient/Add
Method: POST
{
  "ListName": "sample string 1",
  "RecipientList": [
    {
      "Title": "sample string 1",
      "FirstName": "sample string 2",
      "LastName": "sample string 3",
      "MobileNumber": "sample string 4",
      "EmailAddress": "sample string 5",
      "User1": "sample string 6",
      "User2": "sample string 7",
      "User3": "sample string 8",
      "User4": "sample string 9",
      "User5": "sample string 10",
      "User6": "sample string 11",
      "User7": "sample string 12",
      "User8": "sample string 13",
      "User9": "sample string 14",
      "User10": "sample string 15",
      "When": "2020-02-04T16:23:43.6826425+00:00",
      "LookupTest": true
    },
    {
      "Title": "sample string 1",
      "FirstName": "sample string 2",
      "LastName": "sample string 3",
      "MobileNumber": "sample string 4",
      "EmailAddress": "sample string 5",
      "User1": "sample string 6",
      "User2": "sample string 7",
      "User3": "sample string 8",
      "User4": "sample string 9",
      "User5": "sample string 10",
      "User6": "sample string 11",
      "User7": "sample string 12",
      "User8": "sample string 13",
      "User9": "sample string 14",
      "User10": "sample string 15",
      "When": "2020-02-04T16:23:43.6826425+00:00",
      "LookupTest": true
    }
  ],
  "Duplication": {
    "Fields": "sample string 1",
    "Date": "sample string 2",
    "GenerateDate": true,
    "Limit": 4
  },
  "LookupTest": true
}
```
#### Returns
If there were errors adding the recipients then a list of errors as an array of strings. For example:
```
{
  "Errors":["Error 1", "Error 2"]
}
```
If a look request was made then a list of these errors are also included.
If there duplication errors then a list of recipients that are dupolicated are return.
If there was no problem then the following in returned:
```
{
  "Status": "Success"
}
```

#### Statuses
* 200 - Success
* 400 - Invalid Session. Please ensure you Login first
* 400 - No such list found
* 400 - There was a problem adding the recipients. Please contact OnePoint Global Support
