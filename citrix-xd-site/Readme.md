# Citrix XD Site Deployment Sample

This template demonstrates the creation of a self-contained XD deployment in Azure, creating the following resources:

* XenDesktop Desktop Delivery Controller
* SQL Server
* Citrix License Server
* Citrix Storefront Server
* Citrix Director
* Citrix Netscaler
* Citrix Virtual Desktop Agents (1 RDSH & 1 Server VDI)
* Domain Controller

After deployment, the components are fully configured and a simple XenDesktop site is created in a number of steps:

1. A new user-specified domain is created and the machines are automatically joined to it.
2. The SQL server database is configured and a site is created on the XenDesktop Delivery Controller.
3. The VDAs are provisioned and joined to the new site.
4. A Storefront deployment is created, providing access to published Apps & Desktops.

Click the button below to deploy

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Falexstoddard%2Fazure-quickstart-templates%2Fmaster%2Fcitrix-xd-site%2FmainTemplate.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

Template parameters:

| Name   | Description    |
|:--- |:---|
| vhdStorage | Name of the storage account which will contain the deployed machines (must already exist and house vhds described above). |
| vhdStorageType | Type of the new storage account to be created for OS VHDs. |
| vhdStorageGroup | Existing resource group where 'vhdStorage' exists. |
| vhdStorageGroupNewOrExisting | Determines whether a new account is created or an existing one referenced. |
| publicDnsName | Unique public DNS prefix for the deployment. The fqdn will look something like '<dnsname>.westus.cloudapp.azure.com'. Up to 62 chars, digits or dashes, lowercase, should start with a letter: must conform to '^[a-z][a-z0-9-]{1,61}[a-z0-9]$'. |
| publicIpGroup | Group for the public DNS whether created or existing. |
| publicIpName | Azure name for the public DNS object. |
| publicIpNewOrExisting | Whether a new or existing IP should be used. |
| html5Mode | Determines how HTML5 reciever is activated. |
| vmSize | The size of the virtual machines (default: Standard_A2) |
| domainName | Name of the new domain to be created (e.g. 'contoso.com'.) |
| adminUsername | Domain and Citrix admin username. |
| adminPassword | Domain and Citrix admin password. |
| siteName | Name of the XenDesktop site to be created (e.g. 'AzureSite'.) |
| encodedNetscalerLicense | Base64 encoded Netscaler license file |
| emailAddress | Email address used for generation of certificates and notifications. |
| acmeServer | Let's encrypt server to user for certificate generation. |

