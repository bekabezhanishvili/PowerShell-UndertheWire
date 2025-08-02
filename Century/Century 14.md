## CENTURY - Level 14


### Login Information
- Username: `century14`
- Password: `755`
- Connection: `century14@century.underthewire.tech -p 22`


### Goal
Find the number of times the word "polo" appears in the file on the Desktop


### Commands Used
```powershell
  Get-ChildItem
```
```powershell
   $words = (Get-Content -Path ".\countpolos").split(" ")
```
```powershell
  $words | Where-Object {$_ -eq "polo"} | Measure-Object
```

### Steps to Solve
1. Establish connection via SSH `ssh century14@century.underthewire.tech -p 22`
2. Execute the command `Get-ChildItem` to find the file name on the Desktop
3. Split the content of the file and save it into the variable `$words = (Get-Content -Path ".\countpolos").split(" ")`
4. Execute the command `$words | Where-Object {$_ -eq "polo"} | Measure-Object` to find the number of "polo" in the file on the Desktop
5. Done, password found! The password for the next level is `153`


### Password for Level 15
```powershell
153
```

### Notes
In this level, we used the variable `$words` and stored the result of the command `(Get-Content -Path ".\countpolos").split(" ")` in it. This command reads the content of the file and splits it into an array of words based on spaces. Then, we executed the command `$words | Where-Object {$_ -eq "polo"} | Measure-Object` (with `-eq` operator since it's case sensitive) to find the number of times the word "polo" appears in the file.


### References
- [Learn more about the Get-ChildItem command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.5)
- [Learn more about Variables](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-7.5)
- [Learn more about Arrays](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-7.5)
- [Learn more about Properties](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.5)
- [Learn more about Methods](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-7.5)
- [Learn more about Operators](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7.5)
- [Under the Wire - Century 14](https://underthewire.tech/century-14)