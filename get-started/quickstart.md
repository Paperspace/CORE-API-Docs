# Quickstart

## CORE API HTTP endpoints <a id="paperspace-api-http-endpoints"></a>

You can make requests to the CORE HTTP API directly or if you'd prefer to build your own client instead of using the Node.js library, you can use the Paperspace API HTTP endpoints directly, as described in the API documentation.

### Address for the CORE API HTTP endpoints <a id="address-for-the-paperspace-api-http-endpoints"></a>

If making HTTP requests directly to the Paperspace API endpoints use the following address for each request: `https://api.paperspace.io`

### Authenticating the CORE API for HTTP requests

In order to use the HTTP API directly, you must specify the `x-api-key` header with the value of your API key.

## Programmatic access via the Node.js client

You can use the CORE APIs programmatically by creating a Javascript Node.js application and importing the Node.js module.

We'll be illustrating all examples using [ES5](http://speakingjs.com/es5/ch01.html) syntax and the CommonJS module format. For other systems like Asynchronous Module Definition, consider using a bundler such as Browserify.

First, install the `paperspace-node` package in your project directory using:

```text
$ npm install paperspace-node
```

Within your node.js app you can import the package with:

```text
var paperspace_node = require('paperspace-node');
```

Then create an instance of the client, optionally passing in your API key:

```text
var paperspace = paperspace_node({
  apiKey: '1ba4f98e7c0...' // <- paste your api key here
});
```

-or-

```text
var paperspace = paperspace_node();
```

If you do not pass an apiKey parameter when creating the paperspace object the paperspace-node module will look for the environment variable value named`PAPERSPACE_API_KEY` for an API key, or in the cached api key location created by the `paperspace login` command, `~/.paperspace/config.json`. See the [Authentication](quickstart.md#authentication) section below for more information.

You can get the paperspace-node version programmatically via the VERSION attribute:

```text
var version = paperspace_node.VERSION;
```

### Calling the API programmatically

All of the methods are namespaced by category \("machines.create" or "invoices.show"\) and have the same function signature. For example:

```text
paperspace.machines.create({
  // parameters
}, function (err, res) {
  // callback
});
```

That is, the first argument is a parameters object, and the second is an error-first callback function.

For information on all the methods available, see the API documentation.

### Authenticating the CORE API for Node.js requests <a id="authentication"></a>

For authenticated requests, the Paperspace-Node module will look in three places for an API key:

1. Locally in the file `~/.paperspace/config.json`, which can be created via the Paperspace CLI by executing:

   $ paperspace login

See the section on [Obtaining an API key](obtaining-an-api-key.md) for more information.

1. An environment variable: `PAPERSPACE_API_KEY`. Example:

   $ export PAPERSPACE\_API\_KEY=1ba4f98e7c0... $ paperspace machines show --machineId "ps123abc"

2. A command argument: `--apiKey`. Example:

   $ paperspace machines show --apiKey "1ba4f98e7c0..." --machineId "ps123abc"

