## CENTURY - Level 7


### Login Information
- Username: `century7`
- Password: `197`
- Connection: `century7@century.underthewire.tech -p 22`


### Goal
Find the content of a 'readme' file somewhere located within the contacts, desktop, documents, favorites, music, or videos folder in the user's directory


### Commands Used
```powershell
  cd "C:\users\century7\"
```
```powershell
  Get-ChildItem -Recurse -File -ErrorAction SilentlyContinue
```
```powershell
  Where-Object {$_.Name -like "*readme*"}
```
```powershell
  Get-ChildItem -Recurse -File -ErrorAction SilentlyContinue | Where-Object {$_.Name -like "*readme*"}
```

### Steps to Solve
1. Establish connection via SSH `ssh century7@century.underthewire.tech -p 22`
2. Execute the command `cd "C:\Users\century7\"` to change the directory to the user's profile
3. Execute the command `Get-ChildItem -Recurse -File -ErrorAction SilentlyContinue | Where-Object {$_.Name -like "*readme*"}` to find the file location
4. Execute the command `Get-Content -Path "C:\Users\century7\Downloads\readme.txt"`
5. Check the displayed text
6. Done, password found! The password for the next level is `7points`


### Password for Level 8
```powershell
7points
```

### Notes
In this level, we used what's called a recursive search technique with the command `Get-ChildItem -Recurse -File -ErrorAction SilentlyContinue`. We then piped it to the `Where-Object {$_.Name -like "*readme*"}` command  to find the desired file somewhere in the user's directory. 


### References
- [Learn more about the Get-ChildItem command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.5)
- [Learn more about the Where-Object command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.5)
- [Learn more about Options](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-7.5)
- [Under the Wire - Century 7](https://underthewire.tech/century-7)