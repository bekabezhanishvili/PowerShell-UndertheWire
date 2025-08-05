## CYBORG - Level 4


### Login Information
- Username: `cyborg4`
- Password: `88_objects`
- Connection: `cyborg4@cyborg.underthewire.tech -p 22`


### Goal
Find the PowerShell module name with a version number of 8.9.8.9 and the name of the file on the Desktop


### Commands Used
```powershell
  Get-Module -ListAvailable | Where-Object {$_.Version -eq "8.9.8.9"}
```
```powershell
  Get-ChildItem
```


### Steps to Solve
1. Establish connection via SSH `ssh cyborg4@cyborg.underthewire.tech -p 22`
2. Execute the command `Get-Module -ListAvailable | Where-Object {$_.Version -eq "8.9.8.9"}` to find the PowerShell module with the version number `8.9.8.9`
3. Note the displayed output `bacon`
4. First part of the password found! The first part is `bacon`
5. Execute the command `Get-ChildItem` to get the name of the file on the Desktop
6. Done, final password formed! The password for the next level is `bacon_eggs`


### Password for Level 5
```powershell
bacon_eggs
```

### Notes
In this level, we used the `Get-Module -ListAvailable` command to list all installed PowerShell modules on the system. The `-ListAvailable` parameter allows us to see all installed modules, including those that are not yet loaded (if we had used just the `Get-Module` command, it would only display the modules that are currently loaded in the PowerShell session). Finally, we piped the result to the `Where-Object` command to filter and display only the module whose version is `8.9.8.9`. 


### References
- [Learn more about the Get-Module command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/get-module?view=powershell-7.5)
- [Learn more about Parameters](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-7.5)
- [Learn more about the Where-Object command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.5)
- [Learn more about Operators](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7.5)
- [Under the Wire - Cyborg 4](https://underthewire.tech/cyborg-4)