# Scenario 2: Account lockout

- [ ] Reproduced in my lab

## Ticket

> "Hi, I'm trying to log in to my laptop this morning and it says my account is locked. I didn't do anything different. Can you unlock it?"

## First checks

1. Verify it's really the user requesting. Call them on their known number on file.
2. Ask them if they've changed their password recently or if they use the acocunt on other devices. Old credentials can be causing a lockout from another device.

## Steps

1. On the DC, open Event Viewer and go to Windows Logs, then Security.
2. Filter current log and enter event ID 4740.
3. Open the newest event for the user.
4. Sign out the stale session from the source machine, or update the password in credential manager.
5. In ADUC, find the user and unlock their account.
6. Ask the user to try signing in again.

I unlocked the account AFTER fixing the issue because otherwise the account could get locked again.

## Screenshots
[See Screenshots Here](../screenshots/02-screenshots.md)


## Resolution note

> Account was locked out, I verified it was them by calling the number for them on file. Event 4740 showed lockout source at another PC that had an old password. Signed out the session and unlocked account in ADUC. Confirmed they can log in. Resolved.
