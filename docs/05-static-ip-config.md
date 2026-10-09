# Assigning a Static IP to the Wazuh Server (Rocky Linux)

## Why
Agents connect to the manager by IP. If DHCP changes it, agents disconnect.

## Network details
| Item | Value |
|------|-------|
| Static IP | <e.g. 192.168.x.x/24> |
| Gateway | <gateway> |
| DNS | <dns> |

## Steps
1. List connections and note the connection name and interface:
   nmcli connection show
   ip a
2. Set the static IP (replace the connection name, e.g. ens160):
   sudo nmcli connection modify "<connection-name>" \
     ipv4.method manual \
     ipv4.addresses <IP>/24 \
     ipv4.gateway <gateway> \
     ipv4.dns "<dns>"
3. Apply the changes:
   sudo nmcli connection down "<connection-name>" && sudo nmcli connection up "<connection-name>"
4. Verify:
   ip a
   ping -c 3 8.8.8.8
5. Open `https://<STATIC_IP>` and confirm the dashboard loads.

## Result
Agents can reliably connect to the same manager address after reboots.
