# Scenario 1: Forgotten password

- [x] Reproduced in my lab

## Ticket

> "Hi, I forgot my password and can't log in. I got back from vacation this morning."

## First checks

Verify the user's identity. I'd call the number on file for the user and verify it's actually them.


## Steps

1. Open ADUC
2. Right click the domain, click Find and type their username.
3. Right click the user and select Reset Password.
4. Make a temp password. Check the box for "user must change password at next logon", and if it's locked too, unlock the account.
5. Call user back and tell them their temp password.
6. Confirm they can sign in and made a new password.

## Screenshots
[See Screenshots Here](../screenshots/01-screenshots.md)

## Resolution note

> User had forgotten their password, I verified it was them by calling the number we have on file for them. I went into ADUC and reset their password along with unlocking their account. Resolved.
