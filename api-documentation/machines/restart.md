# Restart

Restart an individual machine. If the machine is already restarting, this action will request the machine be restarted again. This action can only be performed by the user who owns the machine.

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
POST /machines/ps123abc/restart
x-api-key: 1ba4f98e7c0...
# Returns 204 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.restart({
  machineId: 'ps123abc',
}, function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| `machineId` | string | Id of the machine to restart |

