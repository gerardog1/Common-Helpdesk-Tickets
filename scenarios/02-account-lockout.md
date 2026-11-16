# Scenario 2: Account lockout

- [ ] Reproduced in my lab

## Ticket

> "Hi, I'm trying to log in to my laptop this morning and it says my account is locked. I didn't do anything different. Can you unlock it?"

## First checks

1. **Verify the user's identity** by calling the number on file.
2. **Ask whether they changed their password recently** and whether the account is used anywhere else, like a phone, a second PC, or a mapped drive. Something still using an old password is the most common cause of repeat lockouts.

## Steps

1. On the domain controller, open **Event Viewer**, then **Windows Logs**, then **Security**.
2. Click **Filter Current Log...**, enter event ID **4740**, and click OK.
3. Open the newest event for the user. **Caller Computer Name** shows which machine keeps locking the account. (The domain controller acting as PDC emulator has the most complete record.)
4. Fix the source: sign out the stale session, or update the saved password in Credential Manager on that machine.
5. In **Active Directory Users and Computers**, find the user, open the **Account** tab, untick **Unlock account**, and click **Apply**.
6. Ask the user to try again.

I unlock the account **after** fixing the source. Otherwise the stale password locks the account again within minutes.

## Screenshots
[See Screenshots Here](.../screenshots/02-screenshots.md)

## Root cause

After the user's password changed, a session left logged in on another PC kept trying the old password until the account locked.

## Sample ticket note

> Account locked out. Verified identity by calling the number on file. Event 4740 showed the lockout source as a second PC with a session left logged in under the old password. Signed that session out, then unlocked the account. User confirmed login works. Resolved.

## Key takeaways

- Unlocking is only the symptom fix. A repeat lockout means something is still using an old password.
- Event 4740 tells you which computer is the source.
