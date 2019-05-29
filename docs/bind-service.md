This topic describes how to bind a service to the .NET Core sample app.

## Overview

Cloud Foundry offers a marketplace of services that allow you to configure
a third-party service with your app.

To bind a service instance to your app, you must do the following:

1. Create a service broker.
1. Create a service instance.
1. Bind the service instance to your app.

## Create a service broker

1. Run the following command:

        cf create-service-broker rabbitmq small-plan my-rabbitmq

## Create a service instance

1. Run the following command:

        cf create-service rabbitmq

## Bind a service instance to the .NET Core sample app

To bind a service instance to the .NET Core sample app, do the following:

1. Run the following command:

        cf bind-service dotnet-core-sample-app
