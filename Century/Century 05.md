## CENTURY - Level 5


### Login Information
- Username: `century5`
- Password: `15768`
- Connection: `century5@century.underthewire.tech -p 22`


### Goal
Find the short name of the domain that this system belongs to, and the name of the file on the Desktop


### Commands Used
```powershell
  Get-ADDomain
```
```powershell
  Get-ChildItem
```


### Steps to Solve
1. Establish connection via SSH `ssh century5@century.underthewire.tech -p 22`
2. Execute the command `Get-ADDomain` to find the name of the domain
3. Look for the `Name` property value
4. Done, the first part is found! The first part of the password is `underthewire`
5. Execute the command `Get-ChildItem` to list the files on the desktop
6. Check the file's name `3347`
7. Done, final password formed! The password for the next level is `underthewire3347`


### Password for Level 6
```powershell
underthewire3347
```


### References
- [Learn more about the Get-ADDomain command](https://learn.microsoft.com/en-us/powershell/module/activedirectory/get-addomain?view=windowsserver2025-ps)
- [Under the Wire - Century 5](https://underthewire.tech/century-5)