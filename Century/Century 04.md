## CENTURY - Level 4


### Login Information
- Username: `century4`
- Password: `123`
- Connection: `century4@century.underthewire.tech -p 22`


### Goal
Find the name of the file located in the directory on the Desktop that has spaces in its name


### Commands Used
```powershell
  Get-ChildItem
```
```powershell
  Get-ChildItem -Path ".\Can You Open Me"
```


### Steps to Solve
1. Establish connection via SSH `ssh century4@century.underthewire.tech -p 22`
2. Execute the command `Get-ChildItem` to find the directory on the desktop
3. Check the name of the directory `Can You Open Me`
4. Execute the command `Get-ChildItem -Path ".\Can You Open Me"`
5. Check the file's name `15768` 
6. Done, password found! The password for the next level is `15768`


### Password for Level 5
```powershell
15768
```

### Notes
In this level, we placed the path in quotation marks because the name of the directory contains spaces. When a directory or file name has spaces, we must wrap it in quotation marks so that PowerShell can read it correctly.


### References
- [Learn more about Quotation Marks](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-7.5)
- [Under the Wire - Century 4](https://underthewire.tech/century-4)