## Description

### HeadQuarters
Deploy the following resources:

* Resource Group (RG) and Virtual Network (VNet)
* 3 subnets (only DMZ has direct internet access)
* Windows Server with public RDP access [dmz]
* N Windows 11 clients [desk]
* N Linux servers [srvs]
* Gateway for internet access
* Pending: 1 container with a public FQDN and a basic Python web app
* Pending: Private Link to Office

### Office
Deploy the next resources:
* Resource Group (RG) and Virtual Network (VNet)
* 2 subnets (without direct internet access)
* Windows Server with public RDP access [srvs]
* N Window Server [srvs]
* N Windows 11 clients [desk]
* Gateway for internet access
* Pending: 1 container with a public FQDN and a basic Python web app
* Pending: Private Link to HQ