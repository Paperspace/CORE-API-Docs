# List

List information about all machines available to either the current authenticated user or the team, if the user belongs to a team. The list method takes an optional first argument to limit the returned machine objects.

This API supports pagination using `limit` and `skip`. The default limit is 1000 items. To retrieve more than 1000 items, set your `skip` parameter to a multiple of 1000. For example, to retrieve the 3rd page of 1000 items, you would pass `{ limit: 1000, skip: 2000 }`.

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
GET /machines/getMachines
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.list(function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `limit` | number | &lt;optional&gt; | Number of items to return. Defaults to 1000. |
| `skip` | number | &lt;optional&gt; | Number of items in the list to skip. |
| `machineId` | string | &lt;optional&gt;  | Optional machine id to match on. Note: must be specified as "machineId", not "id". |
| `name` | string | &lt;optional&gt;  | Optional name to match on |
| `os` | string | &lt;optional&gt;  | Optional os to match on |
| `ram` | string | &lt;optional&gt;  | Optional ram value to match on |
| `cpus` | number | &lt;optional&gt;  | Optional cpu count to match on |
| `gpu` | string | &lt;optional&gt;  | Optional gpu to match on |
| `storageTotal` | string | &lt;optional&gt;  | Optional storageTotal value to match on |
| `storageUsed` | string | &lt;optional&gt;  | Optional storageUsed value to match on |
| `usageRate` | string | &lt;optional&gt;  | Optional usageRate value to match on |
| `shutdownTimeoutInHours` | number | &lt;optional&gt;  | Optional shutdownTimeoutInHours value to match on |
| `performAutoSnapshot` | boolean | &lt;optional&gt;  | Optional performAutoSnapshot value to match on, either true or false |
| `autoSnapshotFrequency` | string | &lt;optional&gt;  | Optional autoSnapshotFrequency value to match on |
| `autoSnapshotSaveCount` | number | &lt;optional&gt;  | Optional autoSnapshotSaveCount value to match on |
| `agentType` | string | &lt;optional&gt;  | Optional agentType value to match on |
| `dtCreated` | string | &lt;optional&gt;  | Optional datetime created value to match on |
| `state` | string | &lt;optional&gt;  | Optional state value to match on |
| `updatesPending` | boolean | &lt;optional&gt;  | Optional updatesPending value to match on |
| `networkId` | string | &lt;optional&gt;  | Optional networkId to match on |
| `privateIpAddress` | string | &lt;optional&gt;  | Optional privateIpAddress to match on |
| `publicIpAddress` | string | &lt;optional&gt;  | Optional publicIpAddress to match on |
| `region` | string | &lt;optional&gt;  | Optional region to match on |
| `userId` | string | &lt;optional&gt;  | Optional userId to match on |
| `teamId` | string | &lt;optional&gt;  | Optional teamId to match on |
| `scriptId` | string | &lt;optional&gt;  | Optional scriptId to match on |
| `dtLastRun` | string | &lt;optional&gt;  | Optional script datetime last run value to match on |

**Returns:**

\[ machine, ... \] - JSON array of machine objects

Type `array`

```text
//Example return value:
[
  {
    "id": "ps123abc",
    "name": "My Machine",
    "os": "Microsoft Windows Server 2016 Datacenter",
    "ram": "8589938688",
    "cpus": 4,
    "gpu": "GRID K160Q (2GB)",
    "storageTotal": "53687091200",
    "storageUsed": "110080",
    "usageRate": "Air monthly",
    "shutdownTimeoutInHours": 168,
    "shutdownTimeoutForces": false,
    "performAutoSnapshot": false,
    "autoSnapshotFrequency": null,
    "autoSnapshotSaveCount": null,
    "agentType": "WindowsDesktop",
    "dtCreated": "2016-11-18T05:18:29.533Z",
    "state": "ready",
    "updatesPending": false,
    "networkId": "n789ghi",
    "privateIpAddress": "10.64.21.47",
    "publicIpAddress": null,
    "region": "East Coast (NY2)",
    "userId": "u123abc",
    "teamId": "te456def",
    "scriptId": "sc123abc",
    "dtLastRun": "2017-06-30T07:22:49.763Z",
    "dynamicPublicIp": null
  }
]
```

