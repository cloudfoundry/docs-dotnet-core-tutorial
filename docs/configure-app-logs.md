This topic describes how to configure logging for the sample app.

## Overview

{{ product_full }} offers built-in logging for apps. To view app logs in
{{ product_short }}, you must configure the .NET sample app to send app logs
to {{ product_short }} by adding a global error handler that logs to stdout.

## Prerequisites

Before you can configure a global error handler, you must download the
.NET sample app. See [Prepare the app](../prepare-app).

## Add a global error handler to the sample app

To add a global error handler to the .NET sample app, follow the steps below:

1. Navigate to the .NET sample app directory.

1. Open `Global.asax.cs` in a text editor.

1. Add the following to the `Global.asax.cs` file:

      void Application_Error(object sender, EventArgs e)
      {
      Exception lastError = Server.GetLastError();
      Console.WriteLine("Unhandled exception: " + lastError.Message + lastError.StackTrace);
      }

1. Save and close the file.
