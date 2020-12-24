# Start

Start an individual machine. If the machine is already started, this action is a no-op. If the machine is off, it will be booted up. This action can only be performed by the user who owns the machine.

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
POST /machines/ps123abc/start
x-api-key: 1ba4f98e7c0...
# Returns 204 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.start({
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
| `machineId` | string | Id of the machine to start |



