# Stop

Stop an individual machine. If the machine is already stopped or has been shut down, this action is a no-op. If the machine is running, it will be stopped and any users logged in will be immediately kicked out. This action can only be performed by the user who owns the machine.

**Examples**

{% tabs %}
{% tab title="HTTPS" %}
```text
# HTTP request:
https://api.paperspace.io
POST /machines/ps123abc/stop
x-api-key: 1ba4f98e7c0...
# Returns 204 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.stop({
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
| `machineId` | string | Id of the machine to shut down |

