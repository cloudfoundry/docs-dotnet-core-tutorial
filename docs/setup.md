This topic describes how to set up your {{ product_full }} environment
before deploying the .NET sample app.

## Overview

Before you can push your app to {{ product_short }} you need to know the following:

- Your username and password for your Cloud Foundry instance.
- The organization and space where you want to deploy your app. A Cloud Foundry workspace
is organized into organizations, and within them, spaces. As a Cloud Foundry user, you have
access to one or more organizations and spaces.
- The API endpoint for your Cloud Foundry instance. See [Identify your Cloud Foundry API endpoint](#identify-your-cloud-foundry-api-endpoint) below.

## Identify your Cloud Foundry API endpoint

Identify your Cloud Controller API endpoint by running `cf api`.

For example:

``` shell
$ cf api
API endpoint: https://api.example.com (API version: 2.55.0)
```
