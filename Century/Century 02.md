## CENTURY - Level 2


### Login Information
- Username: `century2`
- Password: `10.0.14393.7870`
- Connection: `century2@century.underthewire.tech -p 22`


### Goal
Find the name of the built-in cmdlet that performs a wget-like function within PowerShell and the name of the file on the desktop


### Commands Used
```powershell
  Get-Alias wget
```
```powershell
  Get-ChildItem
```


### Steps to Solve
1. Establish connection via SSH `ssh century2@century.underthewire.tech -p 22`
2. Execute the command `Get-Alias wget` to find the built-in cmdlet
3. Look for the name after wget `wget -> Invoke-WebRequest`
4. First part of the password found! The first part is `invoke-webrequest`
5. As for the second part, execute the command `Get-ChildItem` to list all the files on the desktop
6. Note the name of the displayed file `443`
7. Add the first part of the password and the name of the file together
8. Done, final password formed! The password for the next level is `invoke-webrequest443`


### Password for Level 3
```powershell
invoke-webrequest443
```


### References
- [Learn more about the Get-Alias command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7.5)
- [Learn more about the Get-ChildItem command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.5)
- [Under the Wire - Century 2](https://underthewire.tech/century-2)