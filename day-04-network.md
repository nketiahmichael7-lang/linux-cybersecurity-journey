# Day 4: Understanding My Wazuh Lab Network

## Lab Environment
- Host Operating System: Windows
- Virtualization Software: Oracle VirtualBox
- Wazuh Server Operating System: Ubuntu
- Network Mode: NAT

## Network Configuration
- Ubuntu Wazuh Server IP: 10.0.2.15
- Host IP for Port Forwarding: 127.0.0.1
- Host Port: 8443
- Guest Port: 443
- Dashboard URL: https://localhost:8443

## Network Concepts Learned

### NAT
NAT allows my Ubuntu virtual machine to access external networks through VirtualBox networking.

### Port Forwarding
Port forwarding directs traffic from Windows port 8443 to port 443 on the Ubuntu virtual machine, allowing me to access the Wazuh dashboard from my Windows browser.

## Wazuh Architecture
1. Wazuh Agent collects endpoint events.
2. Wazuh Manager analyzes events and generates alerts.
3. Wazuh Indexer stores and indexes alert data.
4. Wazuh Dashboard displays alerts and security information.

## Day 4 Status
- Wazuh Manager: Running
- Wazuh Indexer: Running
- Wazuh Dashboard: Running
- Dashboard Access: Working

## Security Notes
- Never store passwords or API keys in this repository.
- Use only authorized systems in this lab.
