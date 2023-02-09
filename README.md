# ADModule

The secret to being able to run AD enumeration commands from the AD Powershell module on a system without RSAT installed, is the DLL located in ``C:\Windows\Microsoft.NET\assembly\GAC_64\Microsoft.ActiveDirectory.Management`` on a system that has the RSAT installed. This means that we can just grab the DLL from a system with RSAT and drop it on a system we want to enumerate from that does not have RSAT installed. No need to install RSAT.

This repository contains a Microsoft signed DLL for the ActiveDirectory PowerShell module. Basically just a backup from a Microsoft Windows Server 2019 with RSAT from the following locations:

- C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ActiveDirectory
- C:\Windows\WinSxS\*\Microsoft.ActiveDirectory.Management.dll
- C:\Windows\WinSxS\*\Microsoft.ActiveDirectory.Management.resources.dll

## Usage

````
# clone the repository
git clone https://github.com/l4rm4nd/ADModule

# change directory
cd ADModule

# import dlls and modules
Import-Module .\Microsoft.ActiveDirectory.Management.dll -verbose
Import-Module .\ActiveDirectory.psd1 -Verbose

# list imported ad modules
Get-Command -Module ActiveDirectory

# verify that rsat works
Get-ADDomain
````
