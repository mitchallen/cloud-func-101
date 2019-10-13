cloud-func-101
==
A Google Cloud Func starter project
--

This package was created as a gloud func demo.

## Installation

    $ git clone https://github.com/mitchallen/cloud-func-101.git
  
* * *

## Create a Google Cloud Platform account

* https://cloud.google.com

* * *

## Note about billing

Please note that this demo shows how to use services that Google will bill you for.  New users are given a credit and some services are offered for free, below a minimal use.

Be sure to keep an eye on billing and delete test resources when no longer needed.

See: https://console.cloud.google.com/billing

* * *

## Create a GCP (Google Cloud Platform) project

* https://cloud.google.com

## Install the gcloud CLI (command line interface)

### Mac OS

```
brew cask install google-cloud-sdk
```

* * *

## Initialize a project

```
gcloud init
```

* * *

## Update the components

```
gcloud components update
```

* * *

## Set the region for your Google Cloud Functions

For example, I chose __us-central1__.

```
gcloud config set functions/region us-central1
```

You can also pass in a region as part of the deployment command line, below (i.e. `--region us-central1`).

See also:

* https://cloud.google.com/functions/docs/locations

* * *

## Deploy the function

```
gcloud functions deploy helloGET --runtime nodejs8 --trigger-http
```

In the response you will see a line like this where Google will substitute __REGION__ and __PROJECT-ID__ with your settings.

```
httpsTrigger:
  url: https://REGION-PROJECT-ID.cloudfunctions.net/helloGET
```

* * *

## Test the function

At the command line, use `curl` (substitute the URL returned by the deployment method):

```
curl https://REGION-PROJECT-ID.cloudfunctions.net/helloGET
```

See also:

* https://cloud.google.com/sdk/gcloud/reference/functions/deploy

* * *

## CORS support

The demo includes support for CORS.

Try this `curl` command (substituting your function's URL):

```
curl -i -H "Accept: application/json" \
-H "Content-Type: application/json" \
https://REGION-PROJECT-ID.cloudfunctions.net/helloGET
```

* * *

## npm script

An npm deployment script was added to `package.json`.

```
"scripts": {
  "deploy": "gcloud functions deploy helloGET --runtime nodejs8 --trigger-http"
},
```

Run it with the following command:

```
npm run deploy
```

You can edit it and add a `--region` flag, etc.

* * *

## References

* https://cloud.google.com/functions/docs/tutorials/
* https://cloud.google.com/functions/docs/locations
* https://cloud.google.com/nodejs/docs/setup
* https://cloud.google.com/nodejs/docs/reference/libraries
* https://cloud.google.com/sdk/gcloud/reference/functions/deploy
* https://cloud.google.com/functions/docs/writing/http
* https://github.com/GoogleCloudPlatform/nodejs-docs-samples/tree/master/functions/helloworld

This example shows using `async`:

* https://itnext.io/you-can-now-write-google-cloud-functions-with-node-js-8-bd066ea6d4f5
