## CENTURY - Level 12


### Login Information
- Username: `century12`
- Password: `secret_sauce`
- Connection: `century12@century.underthewire.tech -p 22`


### Goal
Find the description of the computer designated as a Domain Controller and the name of the file on the Desktop


### Commands Used
```powershell
  Get-ADComputer -Filter * -Properties Description
```

### Steps to Solve
1. Establish connection via SSH `ssh century12@century.underthewire.tech -p 22`
2. Execute the command `Get-ADComputer -Filter * -Properties Description` to find the description of the computer designated as Domain Controller
3. Check the `Description`
4. First part of the password found! The first part is "i_authenticate"
5. Execute the command `Get-ChildItem`
6. Done, final password formed! The password for the next level is `i_authenticate_things`


### Password for Level 12
```powershell
i_authenticate_things
```

### Notes
In this level, we used the `Get-ADComputer` command to list all computers in the domain. By adding `-Properties Description` to it we were able to see computer's description


### References
- [Learn more about the Get-ADComputer command](https://learn.microsoft.com/en-us/powershell/module/activedirectory/get-adcomputer?view=windowsserver2025-ps)
- [Learn more about Options](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-7.5)
- [Learn more about Parameters](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-7.5)
- [Under the Wire - Century 12](https://underthewire.tech/century-12)