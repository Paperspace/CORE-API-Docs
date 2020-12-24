# List

List information about all templates available to either the current authenticated user or the team, if the user belongs to a team. The list method takes an optional first argument to limit the returned template objects.

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
GET /templates/getTemplates
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.templates.list(function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `id` | string | &lt;optional&gt;  | Optional template id to match on |
| `name` | string | &lt;optional&gt;  | Optional name to match on |
| `label` | string | &lt;optional&gt;  | Optional label to match on |
| `os` | string | &lt;optional&gt;  | Optional os to match on |
| `dtCreated` | string | &lt;optional&gt;  | Optional datetime created value to match on |
| `teamId` | string | &lt;optional&gt;  | Optional teamId to match on |
| `userId` | string | &lt;optional&gt;  | Optional userId to match on |
| `region` | string | &lt;optional&gt;  | Optional region to match on |

**Returns**

\[ template, ... \] - JSON array of template objects 

Type `array`

```text
// Example return value:
[
 // A public template:
 {
   "id": "t123abc",
   "name": "paperspace/t123abc",
   "label": "Windows 10",
   "os": "Windows 10 (Server 2016)",
   "dtCreated": "2017-01-03T23:41:06.801Z"
 },
 // A team-owned template:
 {
   "id": "t456def",
   "name": "t456def",
   "label": "New Template 1",
   "os": "Ubuntu 14.04.5 LTS; uname: 4.2.0-27-generic; distro: ubuntu; major: 14; minor: 04",
   "teamId": "te456def",
   "userId": null,
   "region": "East Coast (NY2)",
   "dtCreated": "2017-02-06T18:46:44.882Z"
 }
]
```

