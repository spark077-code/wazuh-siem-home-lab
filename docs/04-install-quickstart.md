# Wazuh Server Installation (Quickstart) on Rocky Linux

## Requirements
- OS: Rocky Linux <version>
- RAM: 4 GB minimum (8 GB recommended)
- CPU: 2+ cores
- Internet access from the VM
- Root or sudo access

## Steps

### 1. Update the system
```bash
sudo dnf update -y
sudo dnf install curl -y
```

### 2. Download and run the installer
Check the Wazuh official documentation for the latest version and use it in the URL:
```bash
curl -sO https://packages.wazuh.com/<version>/wazuh-install.sh
sudo bash ./wazuh-install.sh -a
```
The `-a` option installs all components (indexer, server, dashboard) on one machine.

### 3. Save the credentials
At the end of the installation, the admin username and password are printed in the terminal. Save them somewhere safe.

### 4. Access the dashboard
Open in a browser:
```
https://<WAZUH_SERVER_IP>
```
The browser will show a certificate warning (self-signed certificate). Continue to the site and log in.

## Firewall (firewalld)
If the firewall is enabled, allow the Wazuh ports:
```bash
sudo firewall-cmd --permanent --add-port=443/tcp
sudo firewall-cmd --permanent --add-port=1514/tcp
sudo firewall-cmd --permanent --add-port=1515/tcp
sudo firewall-cmd --reload
```
| Port | Purpose |
|------|---------|
| 443 | Dashboard |
| 1514 | Agent communication |
| 1515 | Agent enrollment |

## OVA vs Quickstart
| | OVA | Quickstart |
|---|---|---|
| Setup speed | Fast (prebuilt) | Slower (installs components) |
| Flexibility | Limited | Full control over the OS |
| Best for | Quick labs | Learning how Wazuh is installed |

## Notes
- Take a VM snapshot after a clean install.
- Set a static IP before connecting agents: see [Static IP config](05-static-ip-config.md).
- Never commit the generated credentials to GitHub.
