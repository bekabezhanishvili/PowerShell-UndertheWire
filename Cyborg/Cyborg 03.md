## CYBORG - Level 3


### Login Information
- Username: `cyborg3`
- Password: `172.31.45.167_ipv4`
- Connection: `cyborg3@cyborg.underthewire.tech -p 22`


### Goal
Find the number of users in the Cyborg group in Active Directory and the name of the file on the Desktop


### Commands Used
```powershell
  (Get-ADGroup -Filter * -Properties * | Where-Object {$_.Name -match "cyborg"}).Members.Count
```
```powershell
  Get-ChildItem
```


### Steps to Solve
1. Establish connection via SSH `ssh cyborg3@cyborg.underthewire.tech -p 22`
2. Execute the command `(Get-ADGroup -Filter * -Properties * | Where-Object {$_.Name -match "cyborg"}).Members.Count` to find the number of members in the "Cyborg" group
3. Note the displayed output `88`
4. First part of the password found! The first part is `88`
5. Execute the command `Get-ChildItem` to get the name of the file on the Desktop
6. Done, final password formed! The password for the next level is `88_objects`


### Password for Level 4
```powershell
88_objects
```

### Notes
In this level, we used the `Get-ADGroup` command to retrieve Active Directory group objects. We added the `-Filter *` parameter to retrieve all groups and the `-Properties *` parameter to include all available properties of each group. Then, we piped the result to the `Where-Object` command to filter for the `cyborg` group. After that, we wrapped the entire line in parentheses to access its properties. Finally, we used the `.Members.Count` property to get the total number of users in the `cyborg` group.


### References
- [Learn more about the Get-ADGroup command](https://learn.microsoft.com/en-us/powershell/module/activedirectory/get-adgroup?view=windowsserver2025-ps)
- [Learn more about the Parameters](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-7.5)
- [Learn more about the Where-Object command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.5)
- [Learn more about the Properties](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.5)
- [Under the Wire - Cyborg 3](https://underthewire.tech/cyborg-3)