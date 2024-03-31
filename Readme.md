# Step by Step guide to setup AD through powershell

* Initial configuration using 'sconfig'
	- computer name
	- networking setting

* How to guide installting Active directory using powershell
'''shell

	start powershell
	Install-WindowsFeature AD-Domain-Services -IncludeManagmentTools
	Install-ADDSForest -DomainName cyber.com -InstallDNS

'''

