# Resource Delegations

Create resourceDelegation with limited access, e.g. for users who needs to stream a machine you created. The create method takes a delegation object as the only argument with resource name as key and an object with ids to list resource ids to give access to.

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
POST /resourceDelegations/create
x-api-key: 1ba4f98e7c0...
{
  "machine": {
    "ids": ["m123abc", "m456def"]
  }
}
# Returns 200 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
var delegation = {
  machine: {
    ids: ['m123abc', 'm456def']
  }
};
paperspace.resourceDelegations.create(delegation, function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `machine` | object | &lt;optional&gt; | Optional resource 'machine' to grant access to. |
| `ids` | array | &lt;optional&gt; | Optional list of machine ids to grant access to. |

**Returns**

{ delegation: { machine: \['m123abc', 'm456def', ... \] }, accessToken: 'resource-delegation-token-123abc...', ... } - JSON object with provided delegation and newly generated resourceDelegation access

Token Type `object`

```text
// Example return value:
[
  {
    "delegation": {
      "machine": {
        "ids": [
          "m123abc",
          "m456def"
        ]
      }
    },
    "isEnabled": true,
    "accessTokenId": "resource-delegation-token-123abc123abc123abc123abc123abc123abc123abc123abc123abc123abc",
    "dtCreated": "2019-04-03T12:31:40.061Z",
    "id": 123
  }
]
```

