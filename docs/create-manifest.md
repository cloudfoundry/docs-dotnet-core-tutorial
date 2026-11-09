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
* **Stack**: The root file system for your app. You use the `cflinuxfs4` stack to
instruct {{ product_short }} to host the .NET sample app on a Linux VM.
* **Buildpack**: Provides runtime support for your app. You use the .NET
buildpack when you push the .NET sample app.

## Create an app manifest

To create a basic app manifest, do the following:

1. From the `dotnet-core-hello-world` directory, delete the existing `manifest.yml` file.

1. Copy the following example text and paste it into a new file:

        ---
        applications:
        - name: dotnet-core-hello-world
          memory: 256M
          stack: cflinuxfs4
          buildpacks:
          - dotnet_core_buildpack

1. Name the file `manifest.yml` and save.
