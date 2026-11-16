# Scenario 1: Forgotten password

- [x] Reproduced in my lab

## Ticket

> "Hi, I forgot my password and can't log in. I got back from vacation this morning."

## First checks

1. **Verify the user's identity.** I call the number already on file for them, not a number from the ticket. Anyone can type a name into a ticket, so I only trust contact details I already had.
2. **Confirm they are at their desk in the office.** A password change works differently for someone off the network, so I want to know where they are.


## Steps

1. Open **Active Directory Users and Computers**.
2. Right-click the domain, click **Find...**, type the user's name, and click **Find Now**.
3. Right-click the user and click **Reset Password...**.
4. Type a temporary password. Tick **User must change password at next logon**. If the dialog says the account is locked out, tick **Unlock the user's account**.
5. Click **OK**.
6. Call the user back and read the temporary password over the phone. It never goes in the ticket or an email.
7. The user signs in with it and chooses a new password.

## Screenshots
[See Screenshots Here](../screenshots/01-screenshots.md)

## Root cause

The user forgot their password. Repeated wrong guesses had also locked the account, which is why the unlock box mattered.

## Sample ticket note

> User forgot password after returning from vacation. Verified identity by calling the number on file. Reset the password in Active Directory with "must change at next logon" and unlocked the account (it was locked out). Gave the temporary password by phone. User signed in, set a new password, and confirmed access. Resolved.

## Key takeaways

- Identity first, always.
- Force a password change at next logon, so only the user knows the final password.
- Do not put passwords in tickets.
