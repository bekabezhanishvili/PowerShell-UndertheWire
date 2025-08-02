## CENTURY - Level 9


### Login Information
- Username: `century9`
- Password: `696`
- Connection: `century9@century.underthewire.tech -p 22`


### Goal
Find the 161st element in a file on the Desktop


### Commands Used
```powershell
  Get-ChildItem
```
```powershell
  Get-Content -Path ".\Word_Files.txt"
```
```powershell
  $elements = (Get-Content -Path ".\Word_Files.txt").split(" ")
```
```powershell
  $elements[160]
```

### Steps to Solve
1. Establish connection via SSH `ssh century9@century.underthewire.tech -p 22`
2. Execute the command `Get-ChildItem` to find the file name on the Desktop
3. Split the content of the file and save it into the variable `$elements = (Get-Content -Path ".\Word_Files.txt").split(" ")`
4. Execute the command `$elements[160]` to find the 161 element.
5. Done, password found! The password for the next level is `pierid`


### Password for Level 10
```powershell
pierid
```

### Notes
In this level, we used the variable `$elements` and stored the result of the command `(Get-Content -Path ".\Word_Files.txt").split(" ")` in it. This command reads the content of the file and splits it into an array of elements based on spaces. Then, we executed the indexing operation `$elements[160]` (we indicate index 160 because the indexing starts from 0) to find the 161st element in the file.


### References
- [Learn more about Variables](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-7.5)
- [Learn more about Arrays](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-7.5)
- [Learn more about the Get-Content command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-content?view=powershell-7.5)
- [Learn more about Methods](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-7.5)
- [Under the Wire - Century 9](https://underthewire.tech/century-9)