## CENTURY - Level 1


### Login Information
- Username: `century1`
- Password: `century1`
- Connection: `century1@century.underthewire.tech -p 22`


### Goal
Find the build version of the instance of PowerShell on this system


### Commands Used
```powershell
  $PSVersionTable
```


### Steps to Solve
1. Establish connection via SSH `ssh century1@century.underthewire.tech -p 22`
2. Execute the command `$PSVersionTable` to determine PowerShell build version
3. Look for the name `BuildVersion` and check its value
4. Done, password found! The password for the next level is the value `10.0.14393.7870`


### Password for Level 2
```powershell
10.0.14393.7870
```


### References
- [Learn more about $PSVersionTable](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_powershell_editions?view=powershell-7.5)
- [Under the Wire - Century 1](https://underthewire.tech/century-1)