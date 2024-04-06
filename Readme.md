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


## Add user in AD 

```powershell
New-ADUser -Name "Orion Starchaser" -GivenName "Orion" -Surname "Starchaser" -DisplayName "Orion Starchaser" -EmailAddress "o.starchaser@inlanefreight.local" -AccountPassword (ConvertTo-SecureString -AsPlainText "password" -Force) -ChangePasswordAtLogon $true -SamAccountName "o.starchaser" -UserPrincipalName "o.starchaser@inlanefreight.local" -Path "OU=IT,OU=HQ-NYC,OU=Employees,OU=Corp,DC=inlanefreight,DC=local" -Enabled $true

#below how create user in specific OU "alway reach it from RIGHT to LEFT"
#OU actual path in AD "Corp -> Employees -> HQ-NYC -> IT"

-Path "OU=IT,OU=HQ-NYC,OU=Employees,OU=Corp,DC=inlanefreight,DC=local"
```

## Get AD user 

```powershell
#we can use any attribute in place of name like SAM etc
Get-ADUser -Filter {Name -eq "Mike O'Hare"}
```



