<h1 align="center">
  Vulnerable-AD-Plus
  <br>
</h1>

Create a vulnerable active directory that's allowing you to test most of active directory attacks in local lab

# Main Features
- Randomize Attacks
- Full Coverage of the mentioned attacks
- you need run the script in DC with Active Directory installed 
- Some of attacks require client workstation
  
## Supported Attacks
- Abusing ACLs/ACEs
- Kerberoasting
- AS-REP Roasting
- Abuse DnsAdmins (...)
- Password in AD User comment
- Password Spraying
- DCSync (...)
- Silver Ticket (...)
- Golden Ticket (...)
- Pass-the-Hash (...)
- Pass-the-Ticket (...)
- SMB Signing Disabled
- Bad WinRM permission
- Anonymous LDAP query
- Public SMB Share
- Zerologon (Check version)

## Writeup
Now includes a writeup in the wiki section.

## if you didn't install Active Directory yet , you can try 

```powershell
Install-WindowsFeature -Name AD-Domain-Services
```

```powershell
Install-ADDSForest -CreateDnsDelegation:$false -DatabasePath "C:\\Windows\\NTDS" -DomainMode "7" -DomainName "bypazs.local" -DomainNetbiosName "bypazs" -ForestMode "7" -InstallDns:$true -LogPath "C:\\Windows\\NTDS" -NoRebootOnCompletion:$false -SysvolPath "C:\\Windows\\SYSVOL" -Force:$true
```

## if you already installed Active Directory, just run the script !
- Enable Windows Defender
```
IEX((new-object net.webclient).downloadstring("https://raw.githubusercontent.com/bypazs/vulnerable-AD-plus/master/vulnadplus.ps1"));
```
- Disable Windows Defender
```
IEX((new-object net.webclient).downloadstring("https://raw.githubusercontent.com/bypazs/vulnerable-AD-plus/master/vulnadplusv1.1.ps1"));
```
```
Invoke-VulnAD -UsersLimit 20 -DomainName "bypazs.local"
```
