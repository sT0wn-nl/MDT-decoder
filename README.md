# MDT-decoder
When you find the CustomSettings.ini file of the Microsoft Deployment Toolkit during a pentest, it contains an Active Directory encoded username and password. With the tool below you can recover these credentials.

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
