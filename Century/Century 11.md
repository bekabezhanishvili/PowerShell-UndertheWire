## CENTURY - Level 11


### Login Information
- Username: `century11`
- Password: `windowsupdates110`
- Connection: `century11@century.underthewire.tech -p 22`


### Goal
Find the name of the hidden file somewhere located within the Contacts, Desktop, Documents, Favorites, Music, or Videos folder in the user's directory


### Commands Used
```powershell
  cd "C:\Users\century11\"
```
```powershell
  Get-ChildItem -Recurse -File -Attribute Hidden -ErrorAction SilentlyContinue
```

### Steps to Solve
1. Establish connection via SSH `ssh century11@century.underthewire.tech -p 22`
2. Change to the user's profile directory `cd "C:\Users\century11\"`
3. Execute the command `Get-ChildItem -Recurse -File -Attribute Hidden -ErrorAction SilentlyContinue` to find the hidden file location
4. Check the displayed files
5. Done, password found! The password for the next level is `secret_sauce`


### Password for Level 12
```powershell
secret_sauce
```

### Notes
In this level, we used the `Get-ChildItem` command with the `-Attribute Hidden` option to list all hidden files. The `-ErrorAction SilentlyContinue` parameter suppresses any errors that may appear during search.


### References
- [Learn more about the Get-ChildItem command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.5)
- [Learn more about Options](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-7.5)
- [Under the Wire - Century 11](https://underthewire.tech/century-11)