This topic describes how to create a {{ product_full }} manifest for the .NET sample app.

## Overview

An app manifest is a YAML file that contains information about the app.
When you push the app, {{ product_short }} uses the information in the manifest
to determine how to host the app.

In this topic, you create a basic manifest with the following information
about your app:

* **App name**: A name for your app.
* **Container memory**: The amount of memory required to host your app when you
push it to {{ product_short }}.
* **Stack**: The root file system for your app. You use the `windows` stack to
instruct {{ product_short }} to host the .NET sample app on a Windows VM.
* **Buildpack**: Provides runtime support for your app. You use the Hostable Web Core
(HWC) buildpack when you push the .NET sample app.

    !!! note
        The HWC buildpack is a lighter version of the Internet Information Services (IIS)
        server that contains the core IIS functionality.

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
