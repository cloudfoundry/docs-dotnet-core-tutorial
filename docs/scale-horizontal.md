This topic describes how to scale the .NET Core sample app.

## Overview

Factors such as user load, or the number and nature of tasks performed by a
{{ product_short }} app, can change the disk space and memory the app uses. For
many apps, increasing the available disk space or memory can improve overall
performance. Similarly, running additional instances of an app can allow the app
to handle increases in user load and concurrent requests.

Use the `cf scale` command to scale the .NET Core sample app in the following ways:

- **Horizontal scaling**: Create or destroy instances of the app. Adding more
instances allows your app to handle increased traffic and demand.
- **Vertical scaling**: Change the disk space limit or memory limit that
{{ product_short }} applies to all instances of the app. Adding more disk or
memory resources can improve the overall performance of your app.

## Scale up horizontally

To scale up the .NET Core sample app horizontally, run the following command:

    cf scale dotnet-core-sample -i 3

After you run the above command, {{ product_short }} increases the number of
instances of your app to 3 and returns the following output:

    $ cf scale dotnet-core-sample -i 3
    Scaling app dotnet-core-sample in org my-cf-org / space sample-apps as user@my-domain.com...
    OK

## Scale down horizontally

To scale down the .NET Core sample app horizontally, run the following command:

    cf scale dotnet-core-sample -i 1

After you run the above command, {{ product_short }} decreases the number of
instances of your app to 1 and returns the following output:

    $ cf scale dotnet-core-sample -i 1
    Scaling app dotnet-core-sample in org my-cf-org / space sample-apps as user@my-domain.com...
    OK
