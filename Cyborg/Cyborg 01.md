## CYBORG - Level 1


### Login Information
- Username: `cyborg1`
- Password: `cyborg1`
- Connection: `cyborg1@cyborg.underthewire.tech -p 22`


### Goal
Find the state (geographical location, not the account state) that the user Chris Rogers is from, as stated in Active Directory


### Commands Used
```powershell
  Get-ADUser -Identity "chris.rogers" -Properties * | Select-Object State
```


### Steps to Solve
1. Establish connection via SSH `ssh cyborg1@cyborg.underthewire.tech -p 22`
2. Execute the command `Get-ADUser -Identity "chris.rogers" -Properties * | Select-Object State` to find the 'State' property of the user 'Chris Rogers'
3. Note the displayed output `kansas`
4. Done, password found! The password for the next level is `kansas`


### Password for Level 2
```powershell
kansas
```

### Notes
In this level, we used the `Get-ADUser` command to retrieve information about the user Chris Rogers. We used the `-Identity "chris.rogers"` instead of just typing Chris Rogers because Active Directory typically identifies users by their `UserPrincipalName` or `SamAccountName` (not by their full display name). Then, we added `-Properties *` to access all properties. Finally, we piped the result to `Select-Object State` to display only the `State` field. 


### References
- [Learn more about the Get-ADUser command](https://learn.microsoft.com/en-us/powershell/module/activedirectory/get-aduser?view=windowsserver2025-ps)
- [Learn more about Properties](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.5)
- [Learn more about the Select-Object command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-object?view=powershell-7.5)
- [Under the Wire - Cyborg 1](https://underthewire.tech/cyborg-1)