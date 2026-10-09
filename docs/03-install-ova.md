# Wazuh Server Installation (OVA)

## Requirements
- Hypervisor: VMware Workstation / VirtualBox
- RAM: 4 GB minimum (8 GB recommended)
- CPU: 2+ cores
- Network: <NAT / Bridged>

## Steps
1. Download the Wazuh OVA from the official Wazuh documentation.
2. Import the OVA into the hypervisor (File > Open/Import).
3. Adjust RAM and CPU if needed, then power on the VM.
4. Log in to the VM console with the default credentials from the official docs.
5. Run `ip a` to find the VM IP address.
6. Open `https://<WAZUH_SERVER_IP>` in a browser and log in to the dashboard.

## Notes
- Change default passwords after the first login.
- Take a VM snapshot after a clean install.
