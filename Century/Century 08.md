## CENTURY - Level 8


### Login Information
- Username: `century8`
- Password: `7points`
- Connection: `century8@century.underthewire.tech -p 22`


### Goal
Find the number of unique entries in a file on the Desktop


### Commands Used
```powershell
  Get-ChildItem
```
```powershell
  Get-Content -Path "C:\Users\Century8\Desktop\unique.txt"
```
```powershell
  Get-Unique
```
```powershell
  (Get-Content -Path "C:\Users\Century8\Desktop\unique.txt" | Get-Unique).Count
```

### Steps to Solve
1. Establish connection via SSH `ssh century8@century.underthewire.tech -p 22`
2. Execute the command `Get-ChildItem` to find the file name on the Desktop
3. Execute the command `(Get-Content -Path "C:\Users\Century8\Desktop\unique.txt" | Get-Unique).Count` to determine number of unique entries found in a file on the Desktop
4. Check the displayed number
5. Done, password found! The password for the next level is `696`


### Password for Level 9
```powershell
696
```

### Notes
In this level, we used the `Get-Content` command to read the contents of the file, then piped it to the `Get-Unique` command to filter out duplicate entries (`Get-Unique` removes only consecutive duplicates, so the input must be sorted first for accurate use unless the file is already sorted). Finally, we wrapped the entire pipeline in parentheses and added `.Count` property to find the total number of unique entries.


### References
- [Learn more about Get-Content command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-content?view=powershell-7.5)
- [Learn more about Get-Unique command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-7.5)
- [Learn more about Properties](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.5)
- [Under the Wire - Century 8](https://underthewire.tech/century-8)