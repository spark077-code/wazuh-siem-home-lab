# Assigning a Static IP to the Wazuh Server

## Why
Agents connect to the manager by IP. If DHCP changes it, agents disconnect.

## Network details
| Item | Value |
|------|-------|
| Static IP | <e.g. 192.168.x.x> |
| Gateway | <gateway> |
| DNS | <dns> |

## Steps
1. Check the interface name: `ip a`
2. Edit the network configuration (method depends on the OS).
3. Apply the changes and verify:
   ip a
   ping 8.8.8.8
4. Confirm the dashboard opens on the new IP.

## Result
Agents can reliably connect to the same manager address after reboots.
