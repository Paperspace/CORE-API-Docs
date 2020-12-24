# Create

Create a new Paperspace virtual machine. If you are using an individual account, you will be assigned as the owner of the machine. If you are a team administrator, you must specify the user that should be assigned to the machine, either by specifying a user id, or by providing an email address, password, first name and last name for the creation of a new user on the team. \(The email address must not already be associated with a Paperspace account, otherwise, a user creation error is returned.\)

Note: if you attempt to create a new user along with the machine, the user creation step is executed before the creation of the machine. Therefore, if an error occurs, the user creation step may or may not have succeeded. To deal with this, if an error object is returned from the `machines create` method, subsequently call the `users list` method \(with a search filter specifying the email address\) to check if the user creation step succeeded.

Note: machine creation is not always guaranteed to succeed, due to various possible issues such as machine availability, billing issues, resource issues, or system errors. However, you can call the `machines availability` method to check for current point-in-time availability of a given machine type.

This machine create action can only be performed by an account administrator. \(Team members cannot create machines themselves; only the team administrator may do so.\)

**Examples**

{% tabs %}
{% tab title="HTTP" %}
```text
# HTTP request:
https://api.paperspace.io
POST /machines/createSingleMachinePublic {"region": "East Coast (NY2)", "machineType": "Air", "size": 50, "billingType": "monthly", "machineName": "My Machine 1", "templateId": "t123abc", "assignPublicIp": true, "networkId": "n123abc", "teamId": "te456def", "email": "example@example.com", "password": "secret123", "firstName": "Jon", "lastName": "Snow", "notificationEmail": "example@example.com"}
x-api-key: 1ba4f98e7c0...
# Returns 201 on success
```
{% endtab %}

{% tab title="Node.js" %}
```text
paperspace.machines.create({
  region: 'East Coast (NY2)',
  machineType: 'Air',
  size: 50,
  billingType: 'hourly',
  machineName: 'My Machine 1',
  templateId: 't123abc',
  assignPublicIp: true, // optional - assign a new public ip address
  networkId: 'n123abc', // optional - only if creating on a specific network
  teamId: 'te456def', // optional - required if creating this machine for a team
  email: 'example@example.com', // optional - if creating a new user
  password: 'secret123', // optional - if creating a new user
  firstName: 'Jon', // optional - if creating a new user
  lastName: 'Snow', // optional - if creating a new user
  notificationEmail: 'example@example.com', // optional - address to send a notification when complete
  scriptId: 'sc123abc', // optional - a script to be run on startup
}, function(err, res) {
  // handle error or result
});
```
{% endtab %}
{% endtabs %}

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
      <td style="text-align:left"><code>region</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Name of the region: either &apos;East Coast (NY2)&apos;, &apos;West Coast
        (CA1)&apos;, or &apos;Europe (AMS1)&apos;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>machineType</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Machine type: either &apos;Air&apos;, &apos;Standard&apos;, &apos;Pro&apos;,
          &apos;Advanced&apos;, &apos;GPU+&apos;, &apos;P4000&apos;, &apos;P5000&apos;,
          &apos;P6000&apos;, &apos;V100&apos;, &apos;C1&apos;, &apos;C2&apos;, &apos;C3&apos;,
          &apos;C4&apos;, &apos;C5&apos;, &apos;C6&apos;, &apos;C7&apos;, &apos;C8&apos;,
          &apos;C9&apos;, or &apos;C10&apos;</p>
        <p>Note:
          <br />Windows os templates cannot be used to create CPU-only machine types &apos;C1&apos;
          - &apos;C10&apos;.
          <br />Ubuntu os templates cannot be used to create GRID GPU machine types: &apos;Air&apos;,
          &apos;Standard&apos;, &apos;Pro&apos;, or &apos;Advanced&apos;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>size</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Storage size for the machine in GB</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>billingType</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Either &apos;monthly&apos; or &apos;hourly&apos; billing</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>machineName</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">A memorable name for this machine</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>templateId</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Template id of the template to use for creating this machine</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>assignPublicIp</code>
      </td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">Assign a new public ip address on machine creation. Cannot be used with
        dynamicPublicIp.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>dynamicPublicIp</code>
      </td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">Assigns a new public ip address on machine start and releases it from
        the account on machine stop. Cannot be used with assignPublicIp.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>networkId</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">If creating on a specific network, specify its id</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>teamId</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">If creating the machine for a team, specify the team id</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>userId</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">If assigning to an existing user other than yourself, specify the user
        id (mutually exclusive with email, password, firstName, lastName)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>email</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">If creating a new user for this machine, specify their email address (mutually
        exclusive with userId)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>password</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">If creating a new user, specify their password (mutually exclusive with
        userId)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>firstName</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">If creating a new user, specify their first name (mutually exclusive with
        userId)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>lastName</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">If creating a new user, specify their last name (mutually exclusive with
        userId)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>notificationEmail</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">Send a notification to this email address when complete</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>scriptId</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&lt;optional&gt;
        <br />
      </td>
      <td style="text-align:left">The script id of a script to be run on startup. See the <a href="https://paperspace.github.io/paperspace-node/scripts.md">Script Guide</a> for
        more info on using scripts.</td>
    </tr>
  </tbody>
</table>

**Returns**

The created machine JSON object

```text
// Example return value:
{
  "id": "ps123abc",
  "name": "My Machine",
  "os": null,
  "ram": null,
  "cpus": 1,
  "gpu": null,
  "storageTotal": null,
  "storageUsed": null,
  "usageRate": "Air hourly",
  "shutdownTimeoutInHours": 24,
  "shutdownTimeoutForces": false,
  "performAutoSnapshot": false,
  "autoSnapshotFrequency": null,
  "autoSnapshotSaveCount": null,
  "agentType": "WindowsDesktop",
  "dtCreated": "2017-02-16T20:26:54.880Z",
  "state": "provisioning",
  "updatesPending": false,
  "networkId": null,
  "privateIpAddress": null,
  "publicIpAddress": "169.255.255.254",
  "region": null,
  "userId": "u123abc",
  "teamId": "te456def",
  "scriptId": "sc123abc",
  "dtLastRun": null,
  "dynamicPublicIp": null
}
```

