# Citrix XD Deployment Sample

This template demonstrates creating an XD site in a new AD domain up in the cloud. 
It creates one DC VM, one XD DDC VM and joins it to the domain. Afterwards, XD is installed on the DDC.

This template deploys the following resources:
<ul><li>storage account</li><li>vnet</li><li>public ip</li><li>load balancer</li><li>a DC virtual machine</li><li>DDC virtual machine</li></ul>


Click the button below to deploy

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Falexstoddard%2Fazure-quickstart-templates%2Fmaster%2Fcitrix-xd%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

Template parameters:

| Name   | Description    |
|:--- |:---|
| publicDnsName | The DNS prefix for the public IP address |
| storageAccount | Name of the storage account to create    |
| windowsOSVersion| Windows OS version for the VM, allowed values: 2008-R2-SP1, 2012-Datacenter, 2012-R2-Datacenter. |
| vmSize | The size of the virtual machines (default: Standard_A2) |
| domainName | Domain name (e.g. 'contoso.com') |
| adminUsername | Domain admin username |
| adminPassword | Domain admin password |
| assetLocation | The location of resources such as templates and DSC modules that the script is dependent |
| xdMediaLocation | The location of XenDesktop installation media (typically a container uri) |
| xdBuild | The build number to use from xdMediaLocation. For example, if xdBuild is 10, then 10.zip will be used. |
| portRdp | The RDP point you will use to interact with the DDC. |
| portDebug | The port you will use for active debugging of the DDC. |
| portPowershell | The port you will use for controlling the DDC through powershell. |




