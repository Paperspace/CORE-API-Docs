# List

List information about all networks available to either the current authenticated user or the team, if the user belongs to a team. The list method takes an optional first argument to limit the returned network objects.

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
GET /networks/getNetworks
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.networks.list(function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

```text

```

**Parameters**

| Name | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `id` | string | &lt;optional&gt;  | Optional network id to match on |
| `name` | string | &lt;optional&gt;  | Optional name to match on |
| `region` | string | &lt;optional&gt;  | Optional region to match on |
| `dtCreated` | string | &lt;optional&gt;  | Optional datetime created value to match on |
| `network` | string | &lt;optional&gt;  | Optional network to match on |
| `netmask` | string | &lt;optional&gt;  | Optional netmask to match on |
| `teamId` | string | &lt;optional&gt;  | Optional teamId to match on |

**Returns**

\[ network, ... \] - JSON array of network objects 

Type `array`

```text
//Example return value:
[
  {
    "id": "n123abc",
    "name": "Example Network",
    "region": "East Coast (NY2)",
    "dtCreated": "2016-12-22T16:36:42.613Z",
    "network": "10.64.21.0",
    "netmask": "255.255.255.0",
    "teamId": "te456def"
  }
]
```

