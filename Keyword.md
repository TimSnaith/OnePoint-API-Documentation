## Keyword
The Keyword API's allow you to manage keywords used for managing inbound SMS messages.

### Add
Add a keyword which when detected at the beginning of an inbound message will be sent to your inbox for processing.
```
URL: https://api.1pt.mobi/gateway/api/Keyword/Add
Method: POST
{
  "Keyword": "sample string 1",
  "FinishDate": "2020-02-04T04:55:32.3122889+00:00"
}
```
#### Parameters

Name | Description
---- | -----------
Keyword | The keyword which can be between 3 and 50 characters long can only contain alphanumerics
FinishDate | The date the keyword expires. This should be set in the future.

#### Returns
```
nothing
```
#### Statuses

Status | Description
------ | -----------
200 | Success
400 | Invalid Session. Please ensure you Login first
400 | The keyword is already registered
400 | The keyword must be between 3 and 50 characters long and can only contain alphanumerics
400 | There was a problem registering the keyword. Please contact OnePoint Global Support

### Delete
Delete a keyword.
```
URL: https://api.1pt.mobi/gateway/api/Keyword/Delete?keyword={keyword}
Method: DELETE
```
#### Parameters

Name | Description
---- | -----------
keyword | The keyword that you wish to delete from your account

#### Returns
```
nothing
```
#### Statuses

Status | Description
------ | -----------
200 | Success
400 | Invalid Session. Please ensure you Login first
400 | The keyword is already registered
400 | There was a problem deleting the keyword. Please contact OnePoint Global Support

### List
List all keywords associated with your account.
```
URL: https://api.1pt.mobi/gateway/api/Keyword/List
Method: GET
```
#### Returns
```
[
    { "Keyword":"keyword", "FinishDate", "2020-02-04T04:55:32.3122889+00:00" },
    { "Keyword":"keyword", "FinishDate", "2020-02-04T04:55:32.3122889+00:00" },
    { "Keyword":"keyword", "FinishDate", "2020-02-04T04:55:32.3122889+00:00" },
]
```
#### Statuses

Status | Description
------ | -----------
200 | Success
400 | Invalid Session. Please ensure you Login first
400 | There are no active keywords registered

