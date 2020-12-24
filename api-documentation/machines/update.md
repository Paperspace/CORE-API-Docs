# Update

Update attributes of a machine.

**Examples**

{% tabs %}
{% tab title="HTTPS" %}
```text
# HTTP request:
https://api.paperspace.io
POST /machines/ps123abc/updateMachinePublic {"machineId": "ps123abc", "machineName": "New Machine Name", "shutdownTimeoutInHours": 24, "shutdownTimeoutForces": true, "performAutoSnapshot": true, "autoSnapshotFrequency": "week", "autoSnapshotSaveCount": 4, "dynamicPublicIp": true}
x-api-key: 1ba4f98e7c0...
# Returns 204 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.update({
  machineId: 'ps123abc',
  machineName: 'New Machine Name',
  shutdownTimeoutInHours: 24,
  shutdownTimeoutForces: true,
  performAutoSnapshot: true,
  autoSnapshotFrequency: 'week',
  autoSnapshotSaveCount: 4
}, function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `machineId` | string |  | Id of the machine to update |
| `machineName` | string | &lt;optional&gt;  | New name for the machine |
| `shutdownTimeoutInHours` | number | &lt;optional&gt;  | Number of hours before machine is shutdown if no one is logged in via the Paperspace client |
| `shutdownTimeoutForces` | boolean | &lt;optional&gt;  | Force shutdown at shutdown timeout, even if there is a Paperspace client connection |
| `autoSnapshotFrequency` | number | &lt;optional&gt;  | One of 'hour', 'day', 'week', or null |
| `autoSnapshotSaveCount` | number | &lt;optional&gt;  | Number of snapshots to save |
| `performAutoSnapshot` | boolean | &lt;optional&gt;  | Perform auto snapshots |
| `dynamicPublicIp` | boolean | &lt;optional&gt;  | If true, assigns a new public ip address on machine start and releases it from the account on machine stop |

