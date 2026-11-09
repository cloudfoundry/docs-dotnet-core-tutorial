This topic describes how to scale the .NET sample app.

## Overview

Factors such as user load, or the number and nature of tasks performed by a
{{ product_short }} app, can change the disk space and memory the app uses. For
many apps, increasing the available disk space or memory can improve overall
performance. Similarly, running additional instances of an app can allow the app
to handle increases in user load and concurrent requests.

Use the `cf scale` command to scale the .NET sample app in the following ways:

- **Horizontal scaling**: Create or destroy instances of the app. Adding more
instances allows your app to handle increased traffic and demand.
- **Vertical scaling**: Change the disk space limit or memory limit that
{{ product_short }} applies to all instances of the app. Adding more disk or
memory resources can improve the overall performance of your app.

## Scale up the .NET sample app vertically

You can scale up an app vertically by changing the disk space limit and the
memory limit.

### Scale up disk

Follow the steps below to scale up the disk for the .NET sample app.

1. To scale up the .NET sample app disk, run the following command:

        cf scale dotnet-core-hello-world -k 1G

1. {{ product_short }} must restart your app instances to increase the disk.
When prompted by the CLI, enter `y` to confirm that you want to run this command.

1. {{ product_short }} increases the disk space of all instances of your app to 1&nbsp;GB
and returns the following output:

        $ cf scale dotnet-core-hello-world -k 1G

        This will cause the app to restart. Are you sure you want to scale dotnet-core-hello-world?> y

        Scaling app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK
        Stopping app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        Starting app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...

        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        1 of 1 instances running

        App started


        OK

        Showing health and status for app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        requested state: started
        instances: 1/1
        usage: 256M x 1 instances
        urls: dotnet-core-hello-world.my-domain.com
        stack: cflinuxfs4
        buildpack: dotnet_core_buildpack

             state     since                  cpu    memory          disk           details
        #0   running   2024-01-15T10:19:05Z   0.0%   64.2M of 256M   113.4M of 1G

### Scale up memory limit

Follow the steps below to scale up the memory limit for the .NET sample app.

1. To scale up the .NET sample app memory, run the following command:

        cf scale dotnet-core-hello-world -m 1G

1. {{ product_short }} must restart your app instances to increase the memory limit.
When prompted by the CLI, enter `y` to confirm that you want to run this command.

1. {{ product_short }} increases the memory limit of all instances of your app to 1&nbsp;GB
and returns the following output:

        $ cf scale dotnet-core-hello-world -m 1G

        This will cause the app to restart. Are you sure you want to scale dotnet-core-hello-world?> y

        Scaling app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK
        Stopping app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        Starting app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...

        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        1 of 1 instances running

        App started


        OK

        Showing health and status for app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        requested state: started
        instances: 1/1
        usage: 1G x 1 instances
        urls: dotnet-core-hello-world.my-domain.com
        stack: cflinuxfs4
        buildpack: dotnet_core_buildpack

             state     since                  cpu     memory          disk           details
        #0   running   2024-01-15T10:21:34Z   57.7%   130.5M of 1G    113.4M of 1G

## Scale down the .NET sample app vertically

You can scale an app down vertically by decreasing the disk space limit and the
memory limit.

### Scale down disk

Follow the steps below to scale down the disk for the .NET sample app.

1. To scale down the .NET sample app disk, run the following command:

        cf scale dotnet-core-hello-world -k 512M

1. {{ product_short }} must restart your app instances to decrease the disk.
When prompted by the CLI, enter `y` to confirm that you want to run this command.

1. {{ product_short }} decreases the disk space of all instances of your app to 512&nbsp;MB
and returns the following output:

        $ cf scale dotnet-core-hello-world -k 512M

        This will cause the app to restart. Are you sure you want to scale dotnet-core-hello-world?> y

        Scaling app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK
        Stopping app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        Starting app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...

        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        1 of 1 instances running

        App started


        OK

        Showing health and status for app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        requested state: started
        instances: 1/1
        usage: 1G x 1 instances
        urls: dotnet-core-hello-world.my-domain.com
        stack: cflinuxfs4
        buildpack: dotnet_core_buildpack

             state     since                  cpu     memory          disk             details
        #0   running   2024-01-15T10:28:42Z   64.8%   110.6M of 1G    113.4M of 512M

### Scale down memory

Follow the steps below to scale down the memory limit for the .NET sample app.

1. To scale down the .NET sample app memory limit, run the following command:

        cf scale dotnet-core-hello-world -m 512M

1. {{ product_short }} must restart your app instances to decrease the memory limit.
When prompted by the CLI, enter `y` to confirm that you want to run this command.

1. {{ product_short }} decreases the memory limit of all instances of your app to 512&nbsp;MB
and returns the following output:

        $ cf scale dotnet-core-hello-world -m 512M

        This will cause the app to restart. Are you sure you want to scale dotnet-core-hello-world?> y

        Scaling app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK
        Stopping app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        Starting app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...

        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        0 of 1 instances running, 1 starting
        1 of 1 instances running

        App started


        OK

        Showing health and status for app dotnet-core-hello-world in org my-cf-org / space sample-apps as user@my-domain.com...
        OK

        requested state: started
        instances: 1/1
        usage: 512M x 1 instances
        urls: dotnet-core-hello-world.my-domain.com
        stack: cflinuxfs4
        buildpack: dotnet_core_buildpack

             state     since                  cpu     memory           disk             details
        #0   running   2024-01-15T10:31:26Z   57.3%   100.5M of 512M   113.4M of 512M
