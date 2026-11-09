This topic describes how to view logs for the .NET sample app.

## Overview

{{ product_full }} offers built-in logging for apps. View your app logs
using the Cloud Foundry Command Line Interface (cf CLI).

## View logs using the cf CLI

To view logs using the cf CLI, run the following command:

    cf logs dotnet-core-hello-world --recent

The CLI returns logs from deploying and starting your app.

For example:

    $ cf logs dotnet-core-hello-world --recent
    Retrieving logs for app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...

       2024-01-15T10:59:17.64+0000 [API/0] OUT Created app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673
       2024-01-15T10:59:19.37+0000 [API/0] OUT Updated app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673 ({"route"=>"5fbf9d28-fc89-4e6b-846a-220038076003", :verb=>"add", :relation=>"routes", :related_guid=>"5fbf9d28-fc89-4e6b-846a-220038076003"})
       2024-01-15T10:59:20.53+0000 [API/0] OUT Uploading bits for app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673
       2024-01-15T10:59:27.29+0000 [API/0] OUT Creating build for app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673
       2024-01-15T10:59:28.15+0000 [API/0] OUT Updated app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673 ({"state"=>"STARTED"})
       2024-01-15T10:59:28.28+0000 [STG/0] OUT Downloading dotnet_core_buildpack...
       2024-01-15T10:59:28.34+0000 [STG/0] OUT Downloaded dotnet_core_buildpack
       2024-01-15T10:59:28.41+0000 [STG/0] OUT Cell creating container for instance...
       2024-01-15T10:59:28.98+0000 [STG/0] OUT Cell successfully created container for instance...
       2024-01-15T10:59:29.21+0000 [STG/0] OUT Downloading app package...
       2024-01-15T10:59:29.33+0000 [STG/0] OUT Downloaded app package
       2024-01-15T10:59:30.17+0000 [STG/0] OUT -----> Dotnet-Core Buildpack version 2.4.x
       2024-01-15T10:59:30.17+0000 [STG/0] OUT -----> Supplying Dotnet Core
       2024-01-15T10:59:30.25+0000 [STG/0] OUT -----> Installing dotnet-sdk 8.0.x
       2024-01-15T10:59:45.13+0000 [STG/0] OUT -----> Publish dotnet
       2024-01-15T10:59:45.13+0000 [STG/0] OUT        Microsoft (R) Build Engine version 17.x for .NET
       2024-01-15T10:59:45.13+0000 [STG/0] OUT        Copyright (C) Microsoft Corporation. All rights reserved.
       2024-01-15T10:59:58.42+0000 [STG/0] OUT          Restore completed in 8.12 sec for /tmp/app/dotnet-core-hello-world.csproj.
       2024-01-15T11:00:02.65+0000 [STG/0] OUT          dotnet-core-hello-world -> /tmp/contents/deps/0/dotnet_publish/
       2024-01-15T11:00:03.03+0000 [STG/0] OUT -----> Cleaning staging area
       2024-01-15T11:00:03.04+0000 [STG/0] OUT        Removing .nuget
       2024-01-15T11:00:03.12+0000 [STG/0] OUT        Removing .local
       2024-01-15T11:00:03.20+0000 [STG/0] OUT        Removing dotnet-sdk
       2024-01-15T11:00:04.76+0000 [STG/0] OUT Exit status 0
       2024-01-15T11:00:04.76+0000 [STG/0] OUT Uploading droplet, build artifacts cache...
       2024-01-15T11:00:05.46+0000 [STG/0] OUT Uploaded droplet
       2024-01-15T11:00:05.47+0000 [STG/0] OUT Uploading complete
       2024-01-15T11:00:05.93+0000 [STG/0] OUT Cell stopping instance...
       2024-01-15T11:00:05.93+0000 [STG/0] OUT Cell destroying container for instance...
       2024-01-15T11:00:06.38+0000 [CELL/0] OUT Cell creating container for instance...
       2024-01-15T11:00:07.39+0000 [CELL/0] OUT Cell successfully created container for instance...
       2024-01-15T11:00:07.76+0000 [CELL/0] OUT Downloading droplet...
       2024-01-15T11:00:10.88+0000 [CELL/0] OUT Downloaded droplet
       2024-01-15T11:00:11.06+0000 [CELL/0] OUT Starting health monitoring of container
       2024-01-15T11:00:13.94+0000 [APP/PROC/WEB/0] OUT Hosting environment: Production
       2024-01-15T11:00:13.94+0000 [APP/PROC/WEB/0] OUT Content root path: /home/vcap/deps/0/dotnet_publish
       2024-01-15T11:00:13.94+0000 [APP/PROC/WEB/0] OUT Now listening on: http://0.0.0.0:8080
       2024-01-15T11:00:13.94+0000 [APP/PROC/WEB/0] OUT Application started. Press Ctrl+C to shut down.
       2024-01-15T11:00:14.61+0000 [CELL/0] OUT Container became healthy
       2024-01-15T11:07:39.73+0000 [APP/PROC/WEB/0] OUT info: Microsoft.AspNetCore.Hosting.Diagnostics[1]
       2024-01-15T11:07:39.73+0000 [APP/PROC/WEB/0] OUT       Request starting HTTP/1.1 GET http://dotnet-core-hello-world.my-domain.com/
       2024-01-15T11:07:40.20+0000 [RTR/0] OUT dotnet-core-hello-world.my-domain.com - [2024-01-15T11:07:39.578Z] "GET / HTTP/1.1" 200 0 4750 "-" "Mozilla/5.0" response_time:0.706 app_id:"cec48f94-8a7d-43d5-8115-79a7f7af1673" app_index:"0"
