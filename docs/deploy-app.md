This topic describes how to deploy the .NET sample app to {{ product_full }}.

## Overview

To deploy the .NET sample app to {{ product_short }}, you log in to the Cloud Foundry
Command Line Interface (cf CLI), target the Cloud Controller for your {{ product_short }}
deployment, and push the .NET sample app.

## Push the .NET sample app

To push the .NET sample app to {{ product_short }}, do the following:

1. On the command line, navigate to the directory that contains the .NET sample app.

1. Log in to the cf CLI:

        :::shell
        cf login -a api.EXAMPLE-DOMAIN

    Where `api.EXAMPLE-DOMAIN` is the URL of the Cloud Controller in your
    {{ product_short }} instance.

1. To deploy the .NET sample app, run the following command:

        cf push

1. Wait for your app to stage and start.

1. Navigate to `dotnet-sample-app.EXAMPLE-DOMAIN` to see your running app,
where `EXAMPLE-DOMAIN` is the domain for your {{ product_short }} deployment.
