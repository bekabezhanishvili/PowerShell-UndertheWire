## CENTURY - Level 3


### Login Information
- Username: `century3`
- Password: `invoke-webrequest443`
- Connection: `century3@century.underthewire.tech -p 22`


### Goal
Find the number of files on the desktop


### Commands Used
```powershell
  (Get-ChildItem).Count
```


### Steps to Solve
1. Establish connection via SSH `ssh century3@century.underthewire.tech -p 22`
2. Execute the command `(Get-ChildItem).Count` to find the number of the files on the desktop
3. Note the displayed number
4. Done, password found! The password for the next level is `123`


### Password for Level 4
```powershell
123
```

### Notes
In this level, we placed the `Get-ChildItem` cmdlet in parenthesis and added `.Count` property to it. When we wrap a cmdlet in parentheses, PowerShell runs the cmdlet first and returns the result as an object. In this case, it returned a collection of file items from the current directory. Then we added `.Count` to it, which gave us the total number of files on the Desktop.


### Alternative Solution
1. Execute the command `Get-ChildItem | Measure-Object`


### References
- [Learn more about Properties](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.5)
- [Learn more about the Measure-Object command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-7.5)
- [Under the Wire - Century 3](https://underthewire.tech/century-3)