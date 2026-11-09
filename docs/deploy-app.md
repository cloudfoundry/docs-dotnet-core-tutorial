This topic describes how to deploy the .NET sample app to {{ product_full }}.

## Overview

To deploy the .NET sample app to {{ product_short }}, you log in to the Cloud Foundry
Command Line Interface (cf CLI), target the Cloud Controller for your {{ product_short }}
deployment, and push the .NET sample app.

## Push the .NET sample app

To push the .NET sample app to {{ product_short }}, do the following:

1. From the `dotnet-core-hello-world` directory, log in to the cf CLI:

        cf login -a api.EXAMPLE-DOMAIN

    Where `api.EXAMPLE-DOMAIN` is the URL of the Cloud Controller in your
    {{ product_short }} instance.

1. Target the org and space where you want to deploy the app:

        cf target -o MY-ORG -s MY-SPACE

    Where `MY-ORG` is your org name and `MY-SPACE` is your space name.

1. To deploy the .NET sample app, run the following command:

        cf push

1. Wait for your app to stage and start. The CLI returns output similar to the following
when pushing your app to {{ product_short }}:

        $ cf push
        Pushing app dotnet-core-hello-world to org my-cf-org / space sample-apps as user@my-domain.com...
        Applying manifest file /Users/user/workspace/dotnet-core-hello-world/manifest.yml...

        Updating with these attributes...
          ---
          applications:
          - name: dotnet-core-hello-world
            memory: 256M
            stack: cflinuxfs4
            buildpacks:
            - dotnet_core_buildpack
        Manifest applied

        Packaging files to upload...
        Uploading files...

        Waiting for API to complete processing files...

        Staging app and tracing logs...
           Downloading dotnet_core_buildpack...
           Downloaded dotnet_core_buildpack
           Cell creating container for instance...
           Cell successfully created container for instance...
           Downloading app package...
           Downloaded app package
           -----> Dotnet-Core Buildpack version 2.4.x
           -----> Supplying Dotnet Core
           -----> Installing dotnet-sdk 8.0.x
           -----> Publish dotnet
                  Microsoft (R) Build Engine version 17.x for .NET
                  Copyright (C) Microsoft Corporation. All rights reserved.

                    Restore completed in 8.12 sec for /tmp/app/dotnet-core-hello-world.csproj.
                    dotnet-core-hello-world -> /tmp/contents/deps/0/dotnet_publish/
           -----> Cleaning staging area
                  Removing .nuget
                  Removing .local
                  Removing dotnet-sdk
           Exit status 0
           Uploading droplet, build artifacts cache...
           Uploaded droplet
           Uploading complete

        Waiting for app to start...

        name:                dotnet-core-hello-world
        requested state:     started
        routes:              dotnet-core-hello-world.my-domain.com
        stack:               cflinuxfs4
        buildpacks:
             name                   version
             dotnet_core_buildpack  2.4.x

        type:           web
        sidecars:
        instances:      1/1
        memory usage:   256M
             state     since                  cpu    memory      disk
        #0   running   2024-01-15T10:01:05Z   0.0%   0 of 256M   0 of 1G

1. From the output of your app deployment, locate the route for your app next to `routes:`.
In the example above, the URL is `dotnet-core-hello-world.my-domain.com`. Navigate to the URL
to see your running app.
