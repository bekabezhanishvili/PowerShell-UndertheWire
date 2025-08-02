## CENTURY - Level 13


### Login Information
- Username: `century13`
- Password: `i_authenticate_things`
- Connection: `century13@century.underthewire.tech -p 22`


### Goal
Find the number of words in the file on the Desktop


### Commands Used
```powershell
  Get-ChildItem
```
```powershell
  $words = (Get-Content -Path ".\countmywords").split(" ")
```
```powershell
  $words.Count
```

### Steps to Solve
1. Establish connection via SSH `ssh century13@century.underthewire.tech -p 22`
2. Execute the command `Get-ChildItem` to find the file name on the Desktop
3. Split the content of the file and save it into the variable `$words = (Get-Content -Path ".\countmywords").split(" ")`
4. Execute the command `$words.Count` to find the number of words in the file on the Desktop
5. Done, password found! The password for the next level is `755`


### Password for Level 14
```powershell
755
```

### Notes
In this level, we used the variable `$words` and stored the result of the command `(Get-Content -Path ".\countmywords").split(" ")` in it. This command reads the content of the file and splits it into an array of words based on spaces. Then, we used `$words.Count` to find the number of words in the file.


### References
- [Learn more about the Get-ChildItem command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.5)
- [Learn more about Variables](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-7.5)
- [Learn more about Arrays](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-7.5)
- [Learn more about Properties](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.5)
- [Learn more about Methods](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-7.5)
- [Under the Wire - Century 13](https://underthewire.tech/century-13)