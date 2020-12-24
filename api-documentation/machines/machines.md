# Availability

Get machine availability for the given region and machine type. Note: availability is only provided for the dedicated GPU machine types. Also, not all machine types are available in all regions.

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
GET /machines/getAvailability?region=East%20Coast%20(NY2)&machineType=GPU%2B
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.availability({
  region: 'East Coast (NY2)',
  machineType: 'GPU+',
}, function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| `region` | string | Name of the region: either 'East Coast \(NY2\)', 'West Coast \(CA1\)', or 'Europe \(AMS1\)' |
| `machineType` | string | Machine type: either 'GPU+', 'P4000', 'P5000', 'P6000', or 'V100' |

**Returns**

availability - The availability JSON object, containing a single boolean attribute, "available". A value of true for "available" means machines of that type can currently be requested in that region. A value of false means that requests for that machine type are not currently available in that region. 

Type `object`

```text
//Example return value:
{
  "available": true
}
```

