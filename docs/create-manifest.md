This topic describes how to create a manifest for your app.

## Overview

An app manifest is a YAML file that contains information about the app.
When you push the app, {{ product_name_first }} uses the information in the manifest
to determine how to host the app.

In this topic, you create a basic manifest with the following information
about your app:

* **App name**: Choose a name for your app.
* **Container memory**: When you first push an app to {{ product_name }}, set this
value to at least 2&nbsp;GB. After your app is running, you can adjust this
value to use less memory if needed.
* **Stack**: A stack provides the root file system for an app. Use the `windows`
stack to push a Windows app to {{ product_name }}.
* **Buildpack**: A buildpack provides runtime support for an app. Use the
Hostable Web Core (HWC) buildpack for a .NET app.

## Prerequisite

Before you create an app manifest, you must have an ASP.NET 4.x app.

## Create an app manifest

To create a basic app manifest, follow the steps below:

1. Navigate to the `web.config` directory for your app.

1. Copy the following example text and paste it into a new file:

        applications:
        - name: MY-APP
          memory: 2G
          stack: windows
          buildpack: hwc_buildpack

      Where `MY-APP` is the name of your app.

1. Name the file `manifest.yml` and save.
