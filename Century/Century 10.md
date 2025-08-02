## CENTURY - Level 10


### Login Information
- Username: `century10`
- Password: `pierid`
- Connection: `century10@century.underthewire.tech -p 22`


### Goal
Find the 10th and 8th word (ORDER MATTERS!) of the Windows Update service description and the name of the file on the Desktop


### Commands Used
```powershell
  Get-Service | Where-Object {$_.DisplayName -match "*update*"}
```
```powershell
  Get-WMIObject -Class Win32_Service | Where-Object {$_.Name -match "wuauserv"} | Select-Object *
```
```powershell
  Get-ChildItem
```


### Steps to Solve
1. Establish connection via SSH `ssh century10@century.underthewire.tech -p 22`
2. Execute the command `Get-Service | Where-Object {$_.DisplayName -match "*update*"}` to find the name of the service
3. Execute the command `Get-WMIObject -Class Win32_Service | Where-Object {$_.Name -match "wuauserv"} | Select-Object *` to find every property of the service
4. Look for the `Description` section
5. Find the 10th and the 8th word in the `Description`
6. First part of the password found! The first part is "windowsupdates"
7. Execute the command `Get-ChildItem` to find the name of the file on the Desktop `110`
8. Done, final password formed! The password for the next level is `windowsupdates110`


### Password for Level 11
```powershell
windowsupdates110
```

### Notes
In this level, we used the command `Get-Service | Where-Object {$_.DisplayName -match "*update*"}` to find the name of the service related to Windows Update. After finding the name, we ran the command `Get-WMIObject -Class Win32_Service | Where-Object {$_.Name -match "wuauserv"} | Select-Object *` to view all of its properties and check the description of the service to find the 10th and 8th word.


### References
- [Learn more about the Get-Service command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-service?view=powershell-7.5)
- [Learn more about the Get-WMIObject command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1)
- [Learn more about the Select-Object command](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-object?view=powershell-7.5)
- [Learn more about the WMI](https://learn.microsoft.com/en-us/powershell/scripting/learn/ps101/07-working-with-wmi?view=powershell-7.5)
- [Under the Wire - Century 10](https://underthewire.tech/century-10)