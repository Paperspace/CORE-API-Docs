# Scripts

Creates a new startup script. Optionally specify a machine to use this startup script. For Linux machines, the script should be a bash script. For Windows machines, the script should be a PowerShell script. See the [samples directory](https://github.com/Paperspace/paperspace-node/tree/master/samples) for sample startup scripts for Windows. Note: script data is limited to 16KB per script. See the [Script Guide](script-guide.md) for more info on using scripts.

### Create

**Examples**

```text
paperspace.scripts.create({
  scriptName: 'My Script',
  scriptFile: './my_script_file.sh', // must specify either scriptFile or scriptText
  scriptDescription: 'A startup script', // optional
  isEnabled: true, // optional
  runOnce: false, // optional
  machineId: 'ps123abc', // optional
}, function(err, res) {
  // handle error or result
});
```

```text
# HTTP request:
https://api.paperspace.io
POST /scripts/createScript {"scriptName": "My Script", "scriptDescription": "A startup script", "isEnabled": true, "runOnce": false, "machineId": "ps123abc"}
x-api-key: 1ba4f98e7c0...
(file contents as multipart form data)
# Returns 200 on success
```

**Parameters**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>params</code>
      </td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">
        <p>Script create parameters</p>
        <p><b>Properties</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>cb</code>
      </td>
      <td style="text-align:left">function</td>
      <td style="text-align:left">Node-style error-first callback function</td>
    </tr>
  </tbody>
</table>

**Returns**

script - The created script JSON object 

Type `object`

```text
// Example return value:
{
  "id": "sc123abc",
  "ownerType": "user",
  "ownerId": "u456def",
  "name": "My Script",
  "description": "my_script_file.sh",
  "dtCreated": "2017-06-15T19:22:13.507Z",
  "isEnabled": true,
  "runOnce": false
}
```

### Destroy

Destroys the startup script with the given id. When this action is performed, the script is immediately disassociated from any machines it is assigned to as well.

**Examples**

```text
paperspace.scripts.destroy({
  scriptId: 'sc123abc',
}, function(err, res) {
  // handle error or result
});
```

```text
# HTTP request:
https://api.paperspace.io
POST /scripts/sc123abc/destroy
x-api-key: 1ba4f98e7c0...
# Returns 204 on success
```

**Parameters**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>params</code>
      </td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">
        <p>Script destroy parameters</p>
        <p><b>Properties</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>cb</code>
      </td>
      <td style="text-align:left">function</td>
      <td style="text-align:left">Node-style error-first callback function</td>
    </tr>
  </tbody>
</table>

### List

List information about all scripts assigned to either the current authenticated user or the team, if the user belongs to a team. The list method takes an optional first argument to limit the returned script objects.

**Examples**

```text
paperspace.scripts.list(function(err, res) {
  // handle error or result
});
```

```text
# HTTP request:
https://api.paperspace.io
GET /scripts/getScripts
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```

**Parameters**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Attributes</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>filter</code>
      </td>
      <td style="text-align:left">object</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>An optional filter object to limit the returned script objects</p>
        <p><b>Properties</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>cb</code>
      </td>
      <td style="text-align:left">function</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Node-style error-first callback function</td>
    </tr>
  </tbody>
</table>

**Returns**

\[ script, ... \] - JSON array of script objects 

Type `array`

```text
//Example return value:
[
  {
    "id": "sc123abc",
    "ownerType": "user",
    "ownerId": "u456def",
    "name": "My Script",
    "description": "original file: my_script.sh",
    "dtCreated": "2017-05-30T14:49:16.724Z",
    "isEnabled": true,
    "runOnce": false
  }
]
```

### Show

Show information for the script with the given id, except for the script text. Use the [scripts text](https://paperspace.github.io/paperspace-node/scripts.html#.text) method retrieve the script text.

**Examples**

```text
paperspace.scripts.show({
  scriptId: 'sc123abc',
}, function(err, res) {
  // handle error or result
});
```

```text
# HTTP request:
https://api.paperspace.io
GET /scripts/getScript?scriptId=sc123abc
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```

**Parameters**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>params</code>
      </td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">
        <p>Script show parameters</p>
        <p><b>Properties</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>cb</code>
      </td>
      <td style="text-align:left">function</td>
      <td style="text-align:left">Node-style error-first callback function</td>
    </tr>
  </tbody>
</table>

**Returns**

script - The script JSON object 

Type `object`

```text
//Example return value:
{
  "id": "sc123abc",
  "ownerType": "user",
  "ownerId": "u456def",
  "name": "My Script",
  "description": "original file: my_script.sh",
  "dtCreated": "2017-05-30T14:49:16.724Z",
  "isEnabled": true,
  "runOnce": false
  "machines": [
    {
      "machineId": "ps123abc",
      "dtLastRun": "2017-07-06T12:38:17.325Z"
    },
    {
      "machineId": "ps456def",
      "dtLastRun": null
    }
  ]
}
```

### Text

Gets the text of the script with the given id.

**Examples**

```text
paperspace.scripts.text({
  scriptId: 'sc123abc',
}, function(err, res) {
  // handle error or result
});
```

```text
# HTTP request:
https://api.paperspace.io
GET /scripts/getScriptText?scriptId=sc123abc
x-api-key: 1ba4f98e7c0...
# Returns 200 on success
```

**Parameters**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>params</code>
      </td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">
        <p>Script text parameters</p>
        <p><b>Properties</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>cb</code>
      </td>
      <td style="text-align:left">function</td>
      <td style="text-align:left">Node-style error-first callback function</td>
    </tr>
  </tbody>
</table>

**Returns**

script - The script JSON object 

Type `string`

```text
//Example return value:
"services start nginx"
```

