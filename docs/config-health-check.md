This topic describes how to configure a health check for the .NET sample app.

## Overview

A health check regularly monitors the status of a running {{ product_full }}
app. If {{ product_name }} detects an unhealthy app instance, the app restarts
in a new container.

The default health check monitors that the TCP port for your app is open.
Follow the steps in this topic to configure additional monitoring for your
app health:

* **HTTP health check**: This health check sends a `GET` request to the HTTP
endpoint on the default port for the app. If the app responds with `HTTP 200`,
then the health check determines that the app is healthy.
* **Custom health endpoint**: Configure a custom health endpoint for more
accurate app health reporting.

## Configure HTTP health check

To add an HTTP health check to your app, run the following command:

```
cf push sample-dotnet-app -u http -t 60
```

This command pushes your app with an HTTP health check that has a timeout
value of 60 seconds. The timeout value determines how much time is allowed
to pass between when the app starts and when the app sends its first healthy response.

## Configure a custom health endpoint
