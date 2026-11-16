# Scenario 3: Connected to Wi-Fi, no internet (APIPA)

- [ ] Reproduced in my lab

## Ticket

> "Hey, my laptop connects to the office Wi-Fi, but I can't get on the internet. Chrome says there's no internet connection. It was working fine yesterday."

## First checks

1. Isolate if this issue is only happening to the user. Ask them if anyone else is experiencing this same issue.
2. Ask them if anything has changed since yesterday. Updates, new desk setup, new Wi-Fi, etc.

## Steps

1. Run `ipconfig /all` to see the IP. It shows a 169.254 address (APIPA)
2. Release and renew the IP lease with `ipconfig /release` then `ipconfig /renew`. Renew fails with a DHCP server error.
3. Have them use their phone hotspot as a test. If the laptop is able to get an IP address there, then the laptop itself is fine.
4. On the DHCP server, look at scope statistics, address leases, and any filters.
5. Search the DHCP audit log in System 32 for the laptop's MAC address to see if it's requests are going through.


## Suspicions

- The DHCP server may be the problem. May need fixing or escalation.
- Could be different AP, VLAN, or a MAC filter. Might need to be escalated to network team.

## Sample escalation note

> Laptop connects to Wi-Fi but has an APIPA address. Started after user moved desk. Only this user is affected. ipconfig /release and ipconfig /renew fails with a DHCP error. MAC address not found in DHCP logs. She tried her phone hotspot and she gets a valid IP address
