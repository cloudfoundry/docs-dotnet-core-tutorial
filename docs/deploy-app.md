This topic describes how to deploy the .NET sample app to {{ product_full }}.

## Overview

To deploy the .NET sample app to {{ product_short }}, you use the Cloud Foundry
Command Line Interface (cf CLI). You log in to the cf CLI, target the Cloud Controller
for your {{ product_short }} deployment, and push the .NET sample app.

## Prerequisites

Before you can push the .NET sample app to {{ product_short }}, you must do the following:

- Identify your Cloud Foundry API endpoint. See [Set up environment](../setup/#identify-your-cloud-foundry-api-endpoint).
- Download the .NET sample app. See [Prepare the app](../prepare-app).
- Create a public domain for the .NET sample app. See ?
- Create an app manifest. See [Create a manifest](../create-manifest).

## Push the .NET sample app

To push the .NET sample app to {{ product_short }}, do the following:

1. On the command line, navigate to the directory that contains the .NET sample app.

1. Log in to the cf CLI:

        cf login

1. Run the following command to target your Cloud Controller:

        cf api https://api.EXAMPLE-DOMAIN

    Where `EXAMPLE-DOMAIN` is the domain for your {{ product_short }} deployment.

1. To deploy the .NET sample app, run the following command:

        cf push

1. Wait for your app to stage and start.

1. Navigate to `dotnet-sample-app.EXAMPLE-DOMAIN` to see your running app,
where `EXAMPLE-DOMAIN` is the domain for your {{ product_short }} deployment.
