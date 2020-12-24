# Set access for user

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
GET /machines/:machineId/setMachineAccessPublic?userId=u123abc
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.setAccessForUser({
  machineId: 'ps123abc',
  userId: 'u123abc,
}, function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| `machineId` | string | Id of the machine to enable access |
| `userId` | string | Id of the user to enable machine access for |
| `enab`**l**`eAccess-` | boolean | releases any assigned public ip address for the machine; defaults to false |



