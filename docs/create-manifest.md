This topic describes how to create a manifest for your app.

## Overview

An app manifest is a YAML file that contains information about how to host
your app. When you eventually push your app, Cloud Foundry uses the information
in the manifest to host your app.

## Prerequisite

Before you create an app manifest, you must have an app.

## Create an app manifest

To create a basic app manifest, follow the steps below:

1. Navigate to the `web.config` directory for your app.

1. Copy the following example text and paste it into a new file:

        applications:
        - name: MY-APP
          memory: 2G
          stack: windows
          buildpack: MY-APP-BUILDPACK

      Where:

      * `MY-APP` is the name of your app.
      * `MY-APP-BUILDPACK` is the buildpack for your app. For example, `hwc_buildpack`.

1. Name the file `manifest.yml` and save.
