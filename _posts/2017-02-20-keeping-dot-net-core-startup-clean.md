---
layout: post
title: "Keeping .Net Core Startup Clean"
date: 2017-02-20 18:00:00 UTC
tags: [.Net Core, Services, C#]
---
{% include JB/setup %}

.Net Core made setting up your application much easier with the Startup.cs file. In Startup.cs, you can configure your services, IoC, logging, Exception Handling - all in one file.

<img src="{{ site.url }}/assets/2017-02-20/Startup.PNG" alt="Startup File" style="width: 200px;"/>

As the application grows over time, this file can become more and more difficult to maintain. At this point you will want to break out some of this code into separate files.

Thankfully, you can use the same pattern that is used to configure the application in the first place!

### ConfigureServices

Make your own IServiceCollection extension, and move your services there:

```c#
// MyServicesConfiguration.cs
public static class MyServicesConfiguration
    {
        public static IServiceCollection AddMyServices(this IServiceCollection services)
        {
            services.AddScoped<IDataReader, JSONDataReader>();
            return services;
        }
    }
```

Now the Startup method can simply use your new extension, like so.

```c#
// Startup.cs
public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services.
        services.AddMvc();
        services.AddMyServices();
    }
```

### Configure

The same can be done for the Configure method, roll your own extension and clean this class up.

```c#
// MyApplicationBuilder.cs
public static class MyApplicationBuilder
    {
        public static IApplicationBuilder UseMyCustomConfiguration(this IApplicationBuilder app)
        {
            // Logging, Exception Handling, Routes

            return app;
        }
    }
``` 

```c#
// Startup.cs 
public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
    {
        app.UseMyCustomConfiguration();
    }
```
While this example was basic, it can used to further separate configuration sections based on whatever you need, such as separate modules, domains, etc.