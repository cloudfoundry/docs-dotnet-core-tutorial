This topic describes how to create a manifest for the .NET sample app.

## Overview

An app manifest is a YAML file that contains information about the app.
When you push the app, {{ product_full }} uses the information in the manifest
to determine how to host the app.

In this topic, you create a basic manifest with the following information
about your app:

* **App name**: A name for your app.
* **Container memory**: The amount of memory required to host your app when you
first push it to {{ product_short }}.
* **Stack**: A stack provides the root file system for an app. Use the `windows`
stack to push the .NET sample app to {{ product_short }}.
* **Buildpack**: A buildpack provides runtime support for an app. Use the
Hostable Web Core (HWC) buildpack for the .NET sample app.

## Prerequisite

Before you create the app manifest, you must download the .NET sample app.

## Create an app manifest

To create a basic app manifest, follow the steps below:

1. Navigate to the `web.config` directory for the .NET sample app.

1. Copy the following example text and paste it into a new file:

        applications:
        - name: sample-dotnet-app
          memory: 2G
          stack: windows
          buildpack: hwc_buildpack

1. Name the file `manifest.yml` and save.
