# Step by Step guide to setup AD through PowerShell

## Initial Configuration Using 'sconfig'
- Computer Name
- Networking Setting

## How to Guide Installing Active Directory Using PowerShell

```powershell
start powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagmentTools
Install-ADDSForest -DomainName cyber.com -InstallDNS
```

* Window Server will auto restart
* Need to change it's DNS server, it will reset it to it's loopback address after reset
* Set DC Server to PC DNS Server

```powershell
# get interface interfaceIndex number
 Get-DnsClientServerAddress

# set DNS using obtain interface index
 Set-DnsClientServerAddress -InterfaceIndex 12 -ServerAddresses ("10.0.0.1","10.0.0.2")
 ```


 ## Add client PC in Active directory through Powershell

 ```powershell
 Add-Computer -DomainName egDomain.com -Restart
 ```

 * PC restart

