This topic describes how to view logs for the .NET sample app.

## Overview

{{ product_full }} offers built-in logging for apps. In the .NET sample
app configuration, you configure a global error handler that sends logs
to {{ product_short }}. View your app logs using the Cloud Foundry Command
Line Interface (cf CLI).

## Prerequisites

Before you can view app logs, you must do the following:

1. Configure a global error handler for the sample .NET app. See
[Configure app logging](../configure-app-logs).

1. Push the .NET sample app to {{ product_short }}. See [Deploy the app](../deploy-app).

## View logs using the cf CLI

To view logs using the cf CLI, run the following command:

``` shell
cf logs sample-dotnet-app --recent
```
