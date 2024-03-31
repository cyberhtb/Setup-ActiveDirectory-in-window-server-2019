# Step by Step guide to setup AD through PowerShell

## Initial Configuration Using 'sconfig'
- Computer Name
- Networking Setting

## How to Guide Installing Active Directory Using PowerShell

```powershell
start powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagmentTools
Install-ADDSForest -DomainName cyber.com -InstallDNS