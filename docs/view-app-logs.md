This topic describes how to view logs for the .NET Core sample app.

## Overview

{{ product_full }} offers built-in logging for apps. View your app logs
using the Cloud Foundry Command Line Interface (cf CLI).

## View logs using the cf CLI

To view logs using the cf CLI, run the following command:

``` shell
cf logs dotnet-core-sample --recent
```

The CLI returns logs from deploying and starting your app.

For example:

    $ cf logs dotnet-core-sample --recent
    Retrieving logs for app dotnet-core-sample in org my-cf-org / space sample-apps as user@my-domain.com...

       2019-05-30T14:59:17.64-0700 [API/19] OUT Created app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673
       2019-05-30T14:59:19.37-0700 [API/10] OUT Updated app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673 ({"route"=>"5fbf9d28-fc89-4e6b-846a-220038076003", :verb=>"add", :relation=>"routes", :related_guid=>"5fbf9d28-fc89-4e6b-846a-220038076003"})
       2019-05-30T14:59:20.53-0700 [API/17] OUT Uploading bits for app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673
       2019-05-30T14:59:27.29-0700 [API/15] OUT Creating build for app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673
       2019-05-30T14:59:28.15-0700 [API/15] OUT Updated app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673 ({"state"=>"STARTED"})
       2019-05-30T14:59:28.28-0700 [STG/0] OUT Downloading dotnet_core_buildpack_beta...
       2019-05-30T14:59:28.28-0700 [STG/0] OUT Downloading dotnet_core_buildpack...
       2019-05-30T14:59:28.28-0700 [STG/0] OUT Downloading python_buildpack...
       2019-05-30T14:59:28.28-0700 [STG/0] OUT Downloading php_buildpack...
       2019-05-30T14:59:28.28-0700 [STG/0] OUT Downloading staticfile_buildpack...
       2019-05-30T14:59:28.34-0700 [STG/0] OUT Downloaded dotnet_core_buildpack_beta
       2019-05-30T14:59:28.35-0700 [STG/0] OUT Downloaded staticfile_buildpack
       2019-05-30T14:59:28.35-0700 [STG/0] OUT Downloading binary_buildpack...
       2019-05-30T14:59:28.35-0700 [STG/0] OUT Downloaded dotnet_core_buildpack
       2019-05-30T14:59:28.35-0700 [STG/0] OUT Downloading java_buildpack...
       2019-05-30T14:59:28.35-0700 [STG/0] OUT Downloaded php_buildpack
       2019-05-30T14:59:28.35-0700 [STG/0] OUT Downloading nodejs_buildpack...
       2019-05-30T14:59:28.36-0700 [STG/0] OUT Downloading go_buildpack...
       2019-05-30T14:59:28.36-0700 [STG/0] OUT Downloaded python_buildpack
       2019-05-30T14:59:28.36-0700 [STG/0] OUT Downloading ruby_buildpack...
       2019-05-30T14:59:28.37-0700 [STG/0] OUT Downloaded binary_buildpack
       2019-05-30T14:59:28.40-0700 [STG/0] OUT Downloaded java_buildpack
       2019-05-30T14:59:28.40-0700 [STG/0] OUT Downloaded nodejs_buildpack
       2019-05-30T14:59:28.40-0700 [STG/0] OUT Downloaded go_buildpack
       2019-05-30T14:59:28.41-0700 [STG/0] OUT Downloaded ruby_buildpack
       2019-05-30T14:59:28.41-0700 [STG/0] OUT Cell 78d73e58-9a73-4317-bb61-c56223af688b creating container for instance 6a2aca11-4901-474b-a667-20b548b33d78
       2019-05-30T14:59:28.98-0700 [STG/0] OUT Cell 78d73e58-9a73-4317-bb61-c56223af688b successfully created container for instance 6a2aca11-4901-474b-a667-20b548b33d78
       2019-05-30T14:59:29.21-0700 [STG/0] OUT Downloading app package...
       2019-05-30T14:59:29.33-0700 [STG/0] OUT Downloaded app package (39.1K)
       2019-05-30T14:59:30.17-0700 [STG/0] OUT -----> Dotnet-Core Buildpack version 2.2.12
       2019-05-30T14:59:30.17-0700 [STG/0] OUT -----> Supplying Dotnet Core
       2019-05-30T14:59:30.17-0700 [STG/0] OUT -----> Installing libunwind 1.3.1
       2019-05-30T14:59:30.17-0700 [STG/0] OUT        Copy [/tmp/buildpacks/9c7e595c965cbce6b5775a50b06b3583/dependencies/7cd276dbdcda7e2158dde0f8b48d611f/libunwind-1.3.1-cflinuxfs3-96d2f3d0.tar.gz]
       2019-05-30T14:59:30.25-0700 [STG/0] OUT        using the default SDK
       2019-05-30T14:59:30.25-0700 [STG/0] OUT -----> Installing dotnet-sdk 2.2.204
       2019-05-30T14:59:30.25-0700 [STG/0] OUT        Copy [/tmp/buildpacks/9c7e595c965cbce6b5775a50b06b3583/dependencies/760e6b25c4daac0a09936b87bdfe2082/dotnet-sdk.2.2.204.linux-amd64-cflinuxfs3-3278b7aa.tar.xz]
       2019-05-30T14:59:38.63-0700 [STG/0] OUT -----> Installing dotnet-runtime 2.2.5
       2019-05-30T14:59:38.63-0700 [STG/0] OUT        Copy [/tmp/buildpacks/9c7e595c965cbce6b5775a50b06b3583/dependencies/6c5dba8799428964421de770da9b5df3/dotnet-runtime.2.2.5.linux-amd64-cflinuxfs3-45a01508.tar.xz]
       2019-05-30T14:59:42.14-0700 [STG/0] OUT -----> Finalizing Dotnet Core
       2019-05-30T14:59:42.15-0700 [STG/0] OUT -----> Installing dotnet-runtime 2.2.5
       2019-05-30T14:59:42.15-0700 [STG/0] OUT        Copy [/tmp/buildpacks/9c7e595c965cbce6b5775a50b06b3583/dependencies/6c5dba8799428964421de770da9b5df3/dotnet-runtime.2.2.5.linux-amd64-cflinuxfs3-45a01508.tar.xz]
       2019-05-30T14:59:44.76-0700 [STG/0] OUT -----> Publish dotnet
       2019-05-30T14:59:45.13-0700 [STG/0] OUT        Microsoft (R) Build Engine version 16.0.450+ga8dc7f1d34 for .NET Core
       2019-05-30T14:59:45.13-0700 [STG/0] OUT        Copyright (C) Microsoft Corporation. All rights reserved.
       2019-05-30T14:59:45.13-0700 [STG/0] OUT
       2019-05-30T14:59:58.42-0700 [STG/0] OUT          Restore completed in 12.33 sec for /tmp/app/src/GetStartedDotnet/GetStartedDotnet.csproj.
       2019-05-30T15:00:31.64-0700 [STG/0] OUT          Restore completed in 44.74 sec for /tmp/app/src/GetStartedDotnet/GetStartedDotnet.csproj.
       2019-05-30T15:00:32.21-0700 [STG/0] OUT        /tmp/contents593331762/deps/0/dotnet-sdk/sdk/2.2.204/Sdks/Microsoft.NET.Sdk/targets/Microsoft.NET.Sdk.DefaultItems.targets(153,5): warning NETSDK1071: A PackageReference to 'Microsoft.AspNetCore.All' specified a Version of `2.0.0`. Specifying the version of this package is not recommended. For more information, see https://aka.ms/sdkimplicitrefs [/tmp/app/src/GetStartedDotnet/GetStartedDotnet.csproj]
       2019-05-30T15:00:38.65-0700 [STG/0] OUT          GetStartedDotnet -> /tmp/app/src/GetStartedDotnet/bin/Debug/netcoreapp2.2/ubuntu.18.04-x64/GetStartedDotnet.dll
       2019-05-30T15:00:39.94-0700 [STG/0] OUT          GetStartedDotnet -> /tmp/contents593331762/deps/0/dotnet_publish/
       2019-05-30T15:00:40.03-0700 [STG/0] OUT -----> Cleaning staging area
       2019-05-30T15:00:40.04-0700 [STG/0] OUT        Removing .nuget
       2019-05-30T15:00:42.12-0700 [STG/0] OUT        Removing .local
       2019-05-30T15:00:42.20-0700 [STG/0] OUT        Removing dotnet-sdk
       2019-05-30T15:00:50.67-0700 [STG/0] OUT Exit status 0
       2019-05-30T15:00:50.67-0700 [STG/0] OUT Uploading droplet, build artifacts cache...
       2019-05-30T15:00:50.67-0700 [STG/0] OUT Uploading droplet...
       2019-05-30T15:00:50.67-0700 [STG/0] OUT Uploading build artifacts cache...
       2019-05-30T15:00:50.82-0700 [STG/0] OUT Uploaded build artifacts cache (225B)
       2019-05-30T15:00:51.30-0700 [API/19] OUT Creating droplet for app with guid cec48f94-8a7d-43d5-8115-79a7f7af1673
       2019-05-30T15:00:56.46-0700 [STG/0] OUT Uploaded droplet (41.4M)
       2019-05-30T15:00:56.47-0700 [STG/0] OUT Uploading complete
       2019-05-30T15:00:56.93-0700 [STG/0] OUT Cell 78d73e58-9a73-4317-bb61-c56223af688b stopping instance 6a2aca11-4901-474b-a667-20b548b33d78
       2019-05-30T15:00:56.93-0700 [STG/0] OUT Cell 78d73e58-9a73-4317-bb61-c56223af688b destroying container for instance 6a2aca11-4901-474b-a667-20b548b33d78
       2019-05-30T15:00:57.38-0700 [CELL/0] OUT Cell 796ddb43-1edd-4740-8065-e450c1c5b3ca creating container for instance f79c784a-6f1a-4610-531b-469c
       2019-05-30T15:00:57.58-0700 [STG/0] OUT Cell 78d73e58-9a73-4317-bb61-c56223af688b successfully destroyed container for instance 6a2aca11-4901-474b-a667-20b548b33d78
       2019-05-30T15:00:58.39-0700 [CELL/0] OUT Cell 796ddb43-1edd-4740-8065-e450c1c5b3ca successfully created container for instance f79c784a-6f1a-4610-531b-469c
       2019-05-30T15:00:58.76-0700 [CELL/0] OUT Downloading droplet...
       2019-05-30T15:01:01.88-0700 [CELL/0] OUT Downloaded droplet (41.4M)
       2019-05-30T15:01:02.06-0700 [CELL/0] OUT Starting health monitoring of container
       2019-05-30T15:01:04.94-0700 [APP/PROC/WEB/0] OUT Hosting environment: Production
       2019-05-30T15:01:04.94-0700 [APP/PROC/WEB/0] OUT Content root path: /home/vcap/deps/0/dotnet_publish
       2019-05-30T15:01:04.94-0700 [APP/PROC/WEB/0] OUT Now listening on: http://0.0.0.0:8080
       2019-05-30T15:01:04.94-0700 [APP/PROC/WEB/0] OUT Application started. Press Ctrl+C to shut down.
       2019-05-30T15:01:05.61-0700 [CELL/0] OUT Container became healthy
       2019-05-30T15:07:39.73-0700 [APP/PROC/WEB/0] OUT info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
       2019-05-30T15:07:39.73-0700 [APP/PROC/WEB/0] OUT       Request starting HTTP/1.1 GET http://dotnet-core-sample.my-domain.com/
       2019-05-30T15:07:40.20-0700 [APP/PROC/WEB/0] OUT info: Microsoft.AspNetCore.Mvc.Internal.ControllerActionInvoker[1]
       2019-05-30T15:07:40.20-0700 [APP/PROC/WEB/0] OUT       Executing action method GetStartedDotnet.Controllers.HomeController.Index (GetStartedDotnet) with arguments ((null)) - ModelState is Valid
       2019-05-30T15:07:45.97-0700 [APP/PROC/WEB/0] OUT info: Microsoft.AspNetCore.Mvc.ViewFeatures.Internal.ViewResultExecutor[1]
       2019-05-30T15:07:45.97-0700 [APP/PROC/WEB/0] OUT       Executing ViewResult, running view at path /Views/Home/Index.cshtml.
       2019-05-30T15:07:47.26-0700 [APP/PROC/WEB/0] OUT info: Microsoft.AspNetCore.Mvc.Internal.ControllerActionInvoker[2]
       2019-05-30T15:07:47.26-0700 [APP/PROC/WEB/0] OUT       Executed action GetStartedDotnet.Controllers.HomeController.Index (GetStartedDotnet) in 7138.5019ms
       2019-05-30T15:07:47.28-0700 [RTR/5] OUT dotnet-core-sample.my-domain.com - [2019-05-30T22:07:39.578+0000] "GET / HTTP/1.1" 200 0 4750 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/74.0.3729.169 Safari/537.36" "10.10.66.62:34764" "10.10.149.227:61130" x_forwarded_for:"209.234.137.222, 10.10.66.62" x_forwarded_proto:"http" vcap_request_id:"1b54f77a-f92d-4f6b-4102-d2a28fcc818f" response_time:7.706084071 app_id:"cec48f94-8a7d-43d5-8115-79a7f7af1673" app_index:"0" x_b3_traceid:"4c89f171d5333ec2" x_b3_spanid:"4c89f171d5333ec2" x_b3_parentspanid:"-" b3:"4c89f171d5333ec2-4c89f171d5333ec2"
       2019-05-30T15:07:47.28-0700 [RTR/5] OUT
