## CYBORG - Level 2


### Login Information
- Username: `cyborg2`
- Password: `kansas`
- Connection: `cyborg2@cyborg.underthewire.tech -p 22`


### Goal
Find the host A record IP address for CYBORG718W100N and the name of the file on the Desktop


### Commands Used
```powershell
  Get-DnsServerZone
```
```powershell
  Get-DnsServerResourceRecord -ZoneName "underthewire.tech"
```
```powershell
  Get-DnsServerResourceRecord -ZoneName "underthewire.tech" | Where-Object {$_.HostName -match "CYBORG718W100N"} | Format-List
```
```powershell
  Get-ChildItem
```


### Steps to Solve
1. Establish connection via SSH `ssh cyborg2@cyborg.underthewire.tech -p 22`
2. Execute the command `Get-DnsServerZone` to display the DNS zones configured on the server and find the relevant zone `underthewire.tech`
3. Execute the command `Get-DnsServerResourceRecord -ZoneName underthewire.tech` to find DNS records within that zone
4. Execute the command `Get-DnsServerResourceRecord underthewire.tech | Where-Object {$_.HostName -match "CYBORG718W100N"} | Format-List` to find the record IP address (`RecordData`) for "CYBORG718W100N"
5. First part of the password found! The first part is `172.31.45.167`
6. Execute the command `Get-ChildItem` to get the name of the file on the Desktop
7. Done, final password formed! The password for the next level is `172.31.45.167_ipv4`


### Password for Level 3
```powershell
172.31.45.167_ipv4
```

### Notes
In this level, we used the `Get-DnsServerZone` command, which helped us identify which zone we would work with. Then, we used the `Get-DnsServerResourceRecord -ZoneName "underthewire.tech"` command to list all DNS records within the `underthewire.tech` zone. Finally, we used the command `Get-DnsServerResourceRecord underthewire.tech | Where-Object {$_.HostName -match "CYBORG718W100N"} | Format-List` to filter the DNS records by the `HostName` "CYBORG718W100N" and display its details in a readable format using the `Format-List` command.


### References
- [Learn more about the Get-DnsServerZone command](https://learn.microsoft.com/en-us/powershell/module/dnsserver/get-dnsserverzone?view=windowsserver2025-ps)
- [Learn more about the Get-DnsServerResourceRecord command](https://learn.microsoft.com/en-us/powershell/module/dnsserver/get-dnsserverresourcerecord?view=windowsserver2025-ps)
- [Learn more about the Where-Object command ](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.5)
- [Learn more about the Format-List command ](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-object?view=powershell-7.5)
- [Under the Wire - Cyborg 2](https://underthewire.tech/cyborg-2)