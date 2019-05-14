This topic describes how to deploy the .NET sample app to {{ product_full }}.

## Overview

To deploy the .NET sample app to {{ product_short }}, you use the Cloud Foundry
Command Line Interface (cf CLI). You log in to the cf CLI, target the Cloud Controller
for your {{ product_short }} deployment, and push the .NET sample app.

## Prerequisites

Before you can push the .NET sample app to {{ product_short }}, you must do the following:

- Create a Cloud Foundry account. See [Prerequisites](../prerequisites).
- Configure the Cloud Controller API endpoint. See [Set up environment](../setup).
- Download the .NET sample app. See [Prepare the app](../prepare-app).
- Create a public domain for the .NET sample app. See ?
- Create an app manifest. See [Create a manifest](../create-manifest).

## Push the .NET sample app

To push the .NET sample app to {{ product_short }}, do the following:

1. Log in to the cf CLI:

        cf login

1. Run the following command to target the Cloud Controller:

        cf api api.dotnet-sample-app.EXAMPLE.COM
    Where `EXAMPLE.COM` is the public domain you configured for the .NET sample app.

1. To deploy the .NET sample app, run the following command:

        cf push dotnet-sample-app -s windows -b hwc_buildpack

    !!! note
        By default, {{ product_short }} serves .NET Framework apps with Hostable Web Core
        (HWC). HWC is a lighter version of the Internet Information Services (IIS) server
        that contains the core IIS functionality.

1. Wait for your app to stage and start.

1. Navigate to your app's public domain to confirm that the app is running.
