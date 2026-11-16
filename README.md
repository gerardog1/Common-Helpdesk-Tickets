# IT Help Desk Common Tickets
This project goes over 5 common helpdesk tickets and how I'd go about resolving them. Along with the documentation process.
- After closing a ticket, I'd follow up with the user a day or two later to confirm their issue has not come back.


## Scenarios

| # | Scenario | Tools and concepts | Lab-tested |
|---|----------|--------------------|------------|
| 1 | [Forgotten password](scenarios/01-password-reset.md) | ADUC, verify identity | ☑ |
| 2 | [Account lockout](scenarios/02-account-lockout.md) | AD, Event Viewer (event 4740), stale credentials | ☑ |
| 3 | [Connected to Wi-Fi, no internet (APIPA)](scenarios/03-no-internet-apipa-dhcp.md) | ipconfig, DHCP console and logs, isolating network vs. device | ☑ |
| 4 | [Shared folder access](scenarios/04-shared-folder-access.md) | AD security groups, NTFS permissions | ☑ |
| 5 | [Slow computer](scenarios/05-slow-computer.md) | Task Manager, uptime, easy checks first| N/A |
