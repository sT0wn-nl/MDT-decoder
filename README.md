# MDT-decoder
When you find the CustomSettings.ini file of the Microsoft Deployment Toolkit during a pentest, it contains an Active Directory encoded username and password. In this file you will find decoded crentials, for example:
```
;*****************************************************************************************************
; Update domain information below with customer specific settings
; DomainAdminxxxxx refers to the domain account that can join computers and create/manage objects
; it is not the "Administrator" account or an account with Domain Administrators group membership.
;*****************************************************************************************************
SkipDomainMembership=Yes
JoinDomain=example.local
EncodedDomainAdmin=encoded_domain_username
EncodedDomainAdminDomain=encoded_domainname
EncodedDomainAdminPassword=encoded_password
UserExit=CDT_DecodeExit.vbs
SkipUserData=Yes
UserDataLocation=AUTO
SkipComputerBackup=Yes
ComputerBackupLocation=NONEE
```

With the released tool below you can recover these credentials.

Usage example:

```
c:\temp>cscript mdt-decode.vbs
Microsoft (R) Windows Script Host Version 5.812
Copyright (C) Microsoft Corporation. All rights reserved.

Enter encoded domain> encoded value of EncodedDomainAdminDomain in CustomSettings.ini
Enter encoded username> encoded value of EncodedDomainAdmin in CustomSettings.ini
Enter encoded password> encoded value of EncodedDomainAdminPassword in CustomSettings.ini
=============================
Decoded domain: example.local
Decoded username: Administrator
DomainAdminPassword: plain_text_password
```
## Links
https://docs.microsoft.com/nl-nl/mem/configmgr/mdt/
