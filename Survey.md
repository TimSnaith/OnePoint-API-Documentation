## Survey
The Survey API's allow you to get survey results and assess the status of a survey.

### GetResults
Get your survey results.
```
URL: https://api.1pt.mobi/gateway/api/Survey/GetResults
Method: GET
{
  "Format": "sample string 1",
  "Header": true,
  "Since": "2020-02-04T16:09:42.9927661+00:00",
  "SortOrder": 1,
  "SurveyReference": "sample string 2"
}
```
#### Returns
```
the survey results depending on the format requested.
```
#### Statuses
* 200 - Success
* 400 - Invalid Session. Please ensure you Login first
* 400 - This survey does not exist
* 400 - There was a problem getting the results of the survey
* 400 - No results found since 2020-02-04T16:09:42.9927661+00:00

### GetSnapshot
Get a snapshot of the certain questions results
```
URL: https://api.1pt.mobi/gateway/api/Survey/GetSnapshot
Method: GET
{
  "SurveyReference": "sample string 1",
  "SortOrder": 2
}
```
#### Returns
```
The snapshot of a question varies depending on the type of question.
```
#### Statuses
* 200 - Success
* 400 - Invalid Session. Please ensure you Login first
* 400 - This survey does not exist
* 400 - There was a problem processing the survey snapshot
* 400 - The survey has not yet shown any activity
* 400 - The sortOrder is out of range - if must be between 1 and the number of questions

### Status
Get the status of your survey.
```
URL: https://api.1pt.mobi/gateway/api/Survey/Status?surveyReference={surveyReference}
Method: POST
```
#### Returns
```
{
   "Recipients": "recipientCount",
   "Anomalyies": "anomalyCount",
   "Completed": "completionCount",
   "Started": "startedCount",
   "Delivered": "deliveredCount",
   "Abandoned": "abandonedCount",
   "Outstanding": "outstandingCount"
}
```
#### Statuses
* 200 - Success
* 400 - Invalid Session. Please ensure you Login first
* 400 - This survey does not exist
* 400 - The survey has not yet shown any activity
* 400 - The sortOrder is out of range - if must be between 1 and the number of questions


