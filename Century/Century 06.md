## CENTURY - Level 6


### Login Information
- Username: `century6`
- Password: `underthewire3347`
- Connection: `century6@century.underthewire.tech -p 22`


### Goal
Find the number of folders on the desktop


### Commands Used
```powershell
  (Get-ChildItem -Directory).Count
```


### Steps to Solve
1. Establish connection via SSH `ssh century6@century.underthewire.tech -p 22`
2. Execute the command `(Get-ChildItem -Directory).Count` to count the number of the folders on the desktop
3. Check the displayed number `197`
4. Done, password found! The password for the next level is `197`


### Password for Level 7
```powershell
197
```

### Notes
In this level, we placed the `Get-ChildItem` cmdlet with the `-Directory` option in parenthesis and added `.Count` property to it. When we wrap a cmdlet in parentheses, PowerShell runs the cmdlet first and returns the result as an object. In this case, it returned a collection of file items from the current directory. Then we added `.Count` to it, which gave us the total number of folders on the Desktop.

### Alternative Solution
1. Execute the command `Get-ChildItem -Directory | Measure-Object`


### References
- [Learn more about Properties](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.5)
- [Learn more about the Measure-Object command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-7.5)
- [Under the Wire - Century 6](https://underthewire.tech/century-6)