This topic describes how to deploy the .NET Core sample app to {{ product_full }}.

## Overview

To deploy the .NET Core sample app to {{ product_short }}, you log in to the Cloud Foundry
Command Line Interface (cf CLI), target the Cloud Controller for your {{ product_short }}
deployment, and push the .NET Core sample app.

## Push the .NET Core sample app

To push the .NET Core sample app to {{ product_short }}, do the following:

1. From the `get-started-aspnet-core` directory, log in to the cf CLI:

        :::shell
        cf login -a api.EXAMPLE-DOMAIN

    Where `api.EXAMPLE-DOMAIN` is the URL of the Cloud Controller in your
    {{ product_short }} instance.

1. To deploy the .NET Core sample app, run the following command:

        cf push

1. Wait for your app to stage and start. The CLI returns the following output
when pushing your app to {{ product_short }}:

        $ cf push
        Using manifest file /Users/user/workspace/get-started-aspnet-core/manifest.yml

        Using stack cflinuxfs3...
        OK
        Creating app dotnet-core-sample in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        Using route dotnet-core-sample.my-domain.com
        Binding dotnet-core-sample.my-domain.com to dotnet-core-sample...
        OK

        Uploading dotnet-core-sample...
        Uploading app files from: /Users/user/workspace/get-started-aspnet-core
        Uploading 42K, 53 files
        Done uploading
        OK

        Starting app dotnet-core-sample in org my-cf-org / space sample-apps as user@my-domain.com...
        Downloading dotnet_core_buildpack_beta...
        Downloading dotnet_core_buildpack...
        Downloading python_buildpack...
        Downloading php_buildpack...
        Downloading staticfile_buildpack...
        Downloaded dotnet_core_buildpack_beta
        Downloaded staticfile_buildpack
        Downloading binary_buildpack...
        Downloaded dotnet_core_buildpack
        Downloading java_buildpack...
        Downloaded php_buildpack
        Downloading nodejs_buildpack...
        Downloading go_buildpack...
        Downloaded python_buildpack
        Downloading ruby_buildpack...
        Downloaded binary_buildpack
        Downloaded java_buildpack
        Downloaded nodejs_buildpack
        Downloaded go_buildpack
        Downloaded ruby_buildpack
        Cell 78d73e58-9a73-4317-bb61-c56223af688b creating container for instance 6a2aca11-4901-474b-a667-20b548b33d78
        Cell 78d73e58-9a73-4317-bb61-c56223af688b successfully created container for instance 6a2aca11-4901-474b-a667-20b548b33d78
        Downloading app package...
        Downloaded app package (39.1K)
        -----> Dotnet-Core Buildpack version 2.2.12
        -----> Supplying Dotnet Core
        -----> Installing libunwind 1.3.1
               Copy [/tmp/buildpacks/9c7e595c965cbce6b5775a50b06b3583/dependencies/7cd276dbdcda7e2158dde0f8b48d611f/libunwind-1.3.1-cflinuxfs3-96d2f3d0.tar.gz]
               using the default SDK
        -----> Installing dotnet-sdk 2.2.204
               Copy [/tmp/buildpacks/9c7e595c965cbce6b5775a50b06b3583/dependencies/760e6b25c4daac0a09936b87bdfe2082/dotnet-sdk.2.2.204.linux-amd64-cflinuxfs3-3278b7aa.tar.xz]
        -----> Installing dotnet-runtime 2.2.5
               Copy [/tmp/buildpacks/9c7e595c965cbce6b5775a50b06b3583/dependencies/6c5dba8799428964421de770da9b5df3/dotnet-runtime.2.2.5.linux-amd64-cflinuxfs3-45a01508.tar.xz]
        -----> Finalizing Dotnet Core
        -----> Installing dotnet-runtime 2.2.5
               Copy [/tmp/buildpacks/9c7e595c965cbce6b5775a50b06b3583/dependencies/6c5dba8799428964421de770da9b5df3/dotnet-runtime.2.2.5.linux-amd64-cflinuxfs3-45a01508.tar.xz]
        -----> Publish dotnet
               Microsoft (R) Build Engine version 16.0.450+ga8dc7f1d34 for .NET Core
               Copyright (C) Microsoft Corporation. All rights reserved.

                 Restore completed in 12.33 sec for /tmp/app/src/GetStartedDotnet/GetStartedDotnet.csproj.
                 Restore completed in 44.74 sec for /tmp/app/src/GetStartedDotnet/GetStartedDotnet.csproj.
               /tmp/contents593331762/deps/0/dotnet-sdk/sdk/2.2.204/Sdks/Microsoft.NET.Sdk/targets/Microsoft.NET.Sdk.DefaultItems.targets(153,5): warning NETSDK1071: A PackageReference to 'Microsoft.AspNetCore.All' specified a Version of `2.0.0`. Specifying the version of this package is not recommended. For more information, see https://aka.ms/sdkimplicitrefs [/tmp/app/src/GetStartedDotnet/GetStartedDotnet.csproj]
                 GetStartedDotnet -> /tmp/app/src/GetStartedDotnet/bin/Debug/netcoreapp2.2/ubuntu.18.04-x64/GetStartedDotnet.dll
                 GetStartedDotnet -> /tmp/contents593331762/deps/0/dotnet_publish/
        -----> Cleaning staging area
               Removing .nuget
               Removing .local
               Removing dotnet-sdk
        Exit status 0
        Uploading droplet, build artifacts cache...
        Uploading droplet...
        Uploading build artifacts cache...
        Uploaded build artifacts cache (225B)
        Uploaded droplet (41.4M)
        Uploading complete
        Cell 78d73e58-9a73-4317-bb61-c56223af688b stopping instance 6a2aca11-4901-474b-a667-20b548b33d78
        Cell 78d73e58-9a73-4317-bb61-c56223af688b destroying container for instance 6a2aca11-4901-474b-a667-20b548b33d78
        Cell 78d73e58-9a73-4317-bb61-c56223af688b successfully destroyed container for instance 6a2aca11-4901-474b-a667-20b548b33d78

        1 of 1 instances running

        App started


        OK

        App dotnet-core-sample was started using this command `cd ${DEPS_DIR}/0/dotnet_publish && exec ./GetStartedDotnet --server.urls http://0.0.0.0:${PORT}`

        Showing health and status for app dotnet-core-sample in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        requested state: started
        instances: 1/1
        usage: 2G x 1 instances
        urls: dotnet-core-sample.my-domain.com
        last uploaded: Thu May 30 21:59:20 UTC 2019
        stack: cflinuxfs3
        buildpack: dotnet-core

             state     since                    cpu    memory    disk      details
        #0   running   2019-05-30 03:01:05 PM   0.0%   0 of 2G   0 of 1G

1. From the output of your app deployment, locate the route for your app next to `urls:`.
In the example above, the URL is `dotnet-core-sample.my-domain.com`. Navigate to the URL
to see your running app.
