# Utilization

Get machine utilization data for the machine with the given id. Machine upgrades are not represented in utilization data.

**Examples**

{% tabs %}
{% tab title="HTTPS" %}
```text
# HTTP request:
https://api.paperspace.io
GET /machines/getUtilization?machineId=ps123abc&billingMonth=2017-08
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.utilization({
  machineId: 'ps123abc',
  billingMonth: '2017-08',
}, function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| `machineId` | string | Id of the machine to get utilization data for |
| `billingMonth` | string | Billing period to query in `YYYY-MM` format |

**Returns**

utilization - The utilization JSON object

Type `object`

```text
//Example return value:
{
  "machineId": "ps123abc",
  "utilization": {
    "machineId": "ps123abc",
    "secondsUsed": 37351.08562622,
    "hourlyRate": "0.40",
    "billingMonth": "2017-08",
  },
  "storageUtilization": {
    "machineId": "ps123abc",
    "secondsUsed": 678400,
    "monthlyRate": "7.00",
    "billingMonth": "2017-08",
  }
}
```

