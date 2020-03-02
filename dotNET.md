## OnePoint Microsoft .NET Client

The OnePoint Microsoft .NET Client makes it easier to access the OnePoint API.

### Nuget Package
You can install a [Nuget Package](https://www.nuget.org/packages/OnePointSRSWebClient/) directly from Visual Studio by using
the Nuget Package Manager and search for OnePoint. The OnePointSRSWebClient should be available in the list.

### Using the .NET Client
The Client can be referenced through the following library;
```
using OnePointSRSWebClient;
```
As an example to use the client in code:
```
    Client client = new Client();
    if (client.Login()) 
    {
        bool isSent = client.SendMessage("Brand", "12345678901", "Test message");
        client.Logout();
    }
```

It requires a number of things to set up in the config file for the .NET application.
```
    <add key="OnePoint.SmsUsername" value="username" />
    <add key="OnePoint.SmsPassword" value="password" />
    <add key="OnePoint.SmsHost" value="https://api.1pt.mobi/gateway/" />
```
The client currently supports sending single messages, sending multiple messages and generating TinyUrl's.
It will be extended to support other server side capabilities in the near future.
