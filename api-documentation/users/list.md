# List

List information about all users available to either the current authenticated user or the team, if the user belongs to a team. The list method takes an optional first argument to limit the returned user objects.

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
GET /users/getUsers
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.users.list(function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `id` | string | &lt;optional&gt;  | Optional user id to match on |
| `email` | string | &lt;optional&gt;  | Optional email to match on |
| `firstname` | string | &lt;optional&gt;  | Optional firstname to match on |
| `lastname` | string | &lt;optional&gt;  | Optional lastname to match on |
| `dtCreated` | string | &lt;optional&gt;  | Optional datetime created value to match on |
| `teamId` | string | &lt;optional&gt;  | Optional teamId to match on |

**Returns**

\[ user, ... \] - JSON array of user objects

Type `array`

```text
//Example return value:
[
  {
    "id": "u123abc",
    "email": "jon@example.com",
    "firstname": "Jon",
    "lastname": "Snow",
    "dtCreated": "2017-04-15T16:20:59.609Z",
    "teamId": "te456def"
  },
  {
    "id": "u789ghi",
    "email": "jeff@example.com",
    "firstname": "Jeff",
    "lastname": "Green",
    "dtCreated": "2016-12-07T15:59:09.769Z",
    "teamId": "te456def"
  }
]
```

