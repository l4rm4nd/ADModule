# ADModule
Microsoft signed DLL for the ActiveDirectory PowerShell module

Just a backup for the Microsoft's ActiveDirectory PowerShell module from Server 2019 with RSAT and module installed.

## Usage

````
# clone the repository
git clone https://github.com/l4rm4nd/ADModule

# change directory
cd ADModule

# import dlls and modules
Import-Module Microsoft.ActiveDirectory.Management.dll -Verbose
Import-Module ActiveDirectory.psd1 -Verbose

# list imported ad modules
Get-Command -Module ActiveDirectory

# verify that rsat works
Get-ADDomain
````
