This topic describes how to configure an HTTP health check for the .NET sample app.

## Overview

A health check regularly monitors the status of a running {{ product_full }}
app. If {{ product_short }} detects an unhealthy app instance, the app restarts
in a new container.

By default, {{ product_short }} uses a health check to monitor that the TCP port
for your app is open. In this topic, you configure an additional HTTP health check
for the .NET sample app.

The HTTP health check sends a `GET` request to the HTTP endpoint on the default
port for the app. If the app responds with `HTTP 200`, then the health check
determines that the app is healthy.

## Configure HTTP health check

To add an HTTP health check to your app, run the following command:

```
cf push sample-dotnet-app -u http -t 60
```

This command pushes your app with an HTTP health check that has a timeout
value of 60 seconds. The timeout value determines how much time is allowed
to pass between when the app starts and when the app sends its first healthy response.
