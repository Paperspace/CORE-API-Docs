# Destroy

Destroy the machine with the given id. When this action is performed, the machine is immediately shut down and marked for deletion from the datacenter. Any snapshots that were derived from the machine are also deleted. Access to the machine is terminated immediately and billing for the machine is prorated to the hour. This action can only be performed by the user who owns the machine, or in the case of a team, the team administrator.

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
POST /machines/ps123abc/destroyMachine
x-api-key: 1ba4f98e7c0...
# Returns 204 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.destroy({
  machineId: 'ps123abc',
}, function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `machineId` | string |  | The id of the machine to destroy |
| `releasePublicIp` | boolean | &lt;optional&gt;  | releases any assigned public ip address for the machine; defaults to false |

