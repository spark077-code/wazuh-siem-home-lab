# Wazuh Server Installation (Quickstart)

## Requirements
- OS: <Ubuntu Server 22.04 / other supported OS>
- RAM: 4 GB minimum (8 GB recommended)
- Internet access from the VM

## Steps
1. Update the system:
   sudo apt update && sudo apt upgrade -y
2. Download and run the installer (check the official docs for the latest version in the URL):
   curl -sO https://packages.wazuh.com/<version>/wazuh-install.sh
   sudo bash ./wazuh-install.sh -a
3. Save the admin credentials printed at the end of the installation.
4. Open `https://<WAZUH_SERVER_IP>` and log in.

## OVA vs Quickstart
| | OVA | Quickstart |
|---|---|---|
| Setup speed | Fast (prebuilt) | Slower (installs components) |
| Flexibility | Limited | Full control over the OS |
| Best for | Quick labs | Learning how Wazuh is installed |
