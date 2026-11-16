# IT Help Desk Common Tickets
This project goes over 5 common helpdesk tickets and how I'd go about resolving them.

## About
* These are practice tickets, not tickets from a job. I worked through them using AI-simulated users.
* Each write-up ends with a "Reproduce it in a lab" section. I tick the box at the top of a scenario only after I have reproduced it myself in my home lab (Hyper-V with a Windows Server 2022 domain controller and a Windows 11 client).

## Scenarios

| # | Scenario | Tools and concepts | Lab-tested |
|---|----------|--------------------|------------|
| 1 | [Forgotten password](scenarios/01-password-reset.md) | Active Directory Users and Computers, identity verification | ☐ |
| 2 | [Account lockout](scenarios/02-account-lockout.md) | Active Directory, Event Viewer (event 4740), stale credentials | ☐ |
| 3 | [Connected to Wi-Fi, no internet (APIPA)](scenarios/03-no-internet-apipa-dhcp.md) | ipconfig, DHCP console and logs, isolating network vs. device | ☐ |
| 4 | [Shared folder access](scenarios/04-shared-folder-access.md) | AD security groups, NTFS and share permissions | ☐ |
| 5 | [Slow computer](scenarios/05-slow-computer.md) | Task Manager, uptime, cheapest-test-first triage | ☐ |

## Skills shown in these write-ups
* Active Directory user and group management (reset, unlock, group membership)
* DHCP/APIPA and basic network troubleshooting
* File share and permissions troubleshooting
* Event Viewer and Task Manager for finding the cause
* Verifying a user's identity before changing an account
* Clear ticket notes and knowing when to escalate

## More scenarios I have practiced

Walkthroughs only (not lab-tested). Write-ups are coming.

* MFA reset after a new phone
* Shared mailbox access
* New hire setup and offboarding in Microsoft 365
* Suspected phishing and compromised account response
* Outlook closing at startup (add-in)
* Teams microphone not working
* BitLocker recovery key prompt
* VPN will not connect from home
* Printer offline (print spooler)
* OneDrive file will not sync (path too long)
Software install request
Second monitor shows "No Signal"
