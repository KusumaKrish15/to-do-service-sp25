PATCH /tasks/{taskId}
Updates an existing task resource. Only the fields specified in the request body will be updated.

Base Endpoint
{server_url}/tasks/{taskId}
Path Parameters
Parameter

Type

Description

taskId

number

The unique ID of the task to update

Request Body
The request body should contain a JSON object with one or more of the following fields:

Property

Type

Description

user_id

number

(Optional) The ID of the user resource to which this task is assigned

title

string

(Optional) The title or short description of the task

description

string

(Optional) The long description of the task

due_date

string

(Optional) The ISO 8601 format of the date and time the task is due

warning

number

(Optional) The number of minutes relative to the due_date to alert the user of the task. This is normally a negative number to alert the user before the due_date.

Sample Request Body
{
  "title": "Grocery shopping updated",
  "description": "eggs, bacon, gummy bears, milk"
}
Response
A successful response returns the updated task resource.

Sample Response
{
  "user_id": 1,
  "title": "Grocery shopping updated",
  "description": "eggs, bacon, gummy bears, milk",
  "due_date": "2025-02-20T17:00",
  "warning": "-10",
  "id": 1
}
Response Codes
Code

Description

200

OK. The task was successfully updated.

400

Bad Request. The request was malformed.

404

Not Found. The specified task does not exist.

Example Usage
curl -X PATCH {server_url}/tasks/1 \
  -H "Content-Type: application/json" \
  -d '{
        "title": "Grocery shopping updated",
        "description": "eggs, bacon, gummy bears, milk"
      }'
This endpoint allows partial updates to an existing task resource. Only the fields provided in the request body will be updated, while the other fields will remain unchanged.
