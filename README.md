# !NOTE:
It is recommended now to utilize the MSAL .net library : https://github.com/AzureAD/microsoft-authentication-library-for-dotnet

This console app may work with the packages :
```
<packages>
  <package id="BouncyCastle.Crypto.dll" version="1.8.1" targetFramework="net461" />
  <package id="Microsoft.IdentityModel" version="6.1.7600.16394" targetFramework="net461" />
  <package id="Microsoft.IdentityModel.Clients.ActiveDirectory" version="4.3.0" targetFramework="net461" />
  <package id="Microsoft.IdentityModel.JsonWebTokens" version="5.3.0" targetFramework="net461" />
  <package id="Microsoft.IdentityModel.Logging" version="5.3.0" targetFramework="net461" />
  <package id="Microsoft.IdentityModel.Tokens" version="5.3.0" targetFramework="net461" />
  <package id="Newtonsoft.Json" version="11.0.2" targetFramework="net461" />
  <package id="System.IdentityModel.Tokens.Jwt" version="5.3.0" targetFramework="net461" />
</packages>
```

But your mileage may vary. See updates for the ADAL library here: 
https://github.com/AzureAD/azure-activedirectory-library-for-dotnet

# AAD-Console-App-Interactive-Input
This is a .net console application that will utilize the ADAL .net library in order to get an access token and make a get call. You will need to enter your own App ID, Redirect URI, Tenant ID, and HTTP Get Request

The Executable file can be found in the root of this github repo. It is in the zip file called **Interactive Console Application To Make Graph Calls**

Because the only resource this console app requests for is the Microsoft Graph. You will need to modify the resource in the code and recompile the executable file if you're interested in making calls to a different resource. 

# Instructions
Here is a Console Application exe where you can make graph calls using ADAL .NET. 

This console application asks for the **client ID, redirect URI, Tenant ID, and the graph api call** that you’re trying to make.

Note that the Graph API call you’re trying to make will require the whole URL. 
For example, if you’re trying to make the call to get all users with a specific directory role: https://developer.microsoft.com/en-us/graph/docs/api-reference/v1.0/api/directoryrole_list_members

You would get the example request : 

GET https://graph.microsoft.com/v1.0/directoryRoles/{id}/members

And then insert the ID for the directory role you’re interested in. You can get the directory roles using the get request : https://developer.microsoft.com/en-us/graph/docs/api-reference/v1.0/api/directoryrole_list

GET https://graph.microsoft.com/v1.0/directoryRoles

Please note that you cannot use Post commands using this Console App. If you’re interested in making post commands, let me know by filing a github issue and I can look into implementing that functionality. 

**Also Note the AAD App needs the correct permissions and may require admin consent per the call.**

## Support

This is not a Microsoft Supported Github Repository. There are no plans on future support, but if there are any issues feel free to open the an issue against this repo and I will respond back as soon as possible.
