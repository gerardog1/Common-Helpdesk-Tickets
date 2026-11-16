# Scenario 4: Shared folder access

- [ ] Reproduced in my lab

## Ticket

> "Hi, I'm getting a permission error when I try to open the Finance shared drive (S:). I need it for month-end. Can you give me access?"

## First checks

1. Ask what the error says.
2. Get approval from the user's manager or folder owner on the ticket, and ask which permissions they need to have.
3. Find which group controls the folder so I can add the user to that group as opposed to adding the user to the permissions list.

## Steps

1. Open File Explorer on my PC and search the server `\\servername` and right click the Finance folder then go to Properties, Security tab. Note which groups have Modify or Read.
2. Open ADUC and find the matching group and open it's members tab.
3. Click Add and type the User's username and Check Names, hit apply.
4. Ask the user to sign out and back in.
5. Confirm they can open the drive.

## Root cause

The user was not in the security group that grants access to the folder.

## Resolution note

> User received a permission error on the Finance share. Got approval from manager to give them edit access. Added them to the appropriate group in AD. Had them sign out and back in and confirm they can open the folder. Resolved.
