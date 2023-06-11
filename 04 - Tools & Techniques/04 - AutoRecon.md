---
creation date: June 8th 2023
last modified date: June 8th 2023
aliases: []
tags: #🧰
---

Primary Categories: [[04 - Tools & Techniques]] 
Secondary Categories: [[02 - Reconnaissance]] 
Links: [[]] 
Search Tag: #🧰  

---
# AutoRecon  
___

## Description:

AutoRecon is a multi-threaded network reconnaissance tool which performs automated enumeration of services. It is intended as a time-saving tool for use in CTFs and other penetration testing environments (e.g. OSCP). It may also be useful in real-world engagements. The tool works by firstly performing port scans / service detection scans. From those initial results, the tool will launch further enumeration scans of those services using a number of different tools.

## Installation

https://github.com/Tib3rius/AutoRecon
```bash
#!/bin/bash

echo "Updating apt cache..."
sudo apt update

echo "Installing Python3 and pip3..."
sudo apt install -y python3 python3-pip

echo "Installing supporting packages..."
sudo apt install -y seclists curl dnsrecon enum4linux feroxbuster gobuster impacket-scripts nbtscan nikto nmap onesixtyone oscanner redis-tools smbclient smbmap snmp sslscan sipvicious tnscmd10g whatweb wkhtmltopdf

echo "Installing pipx and setting up virtual environment for AutoRecon..."
sudo apt install -y python3-venv
python3 -m pip install --user pipx
python3 -m pipx ensurepath

# Add pipx to PATH if not done automatically
if ! echo $PATH | grep -q '.local/bin'; then
  echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
  source ~/.bashrc
fi

echo "Installing AutoRecon..."
pipx install git+https://github.com/Tib3rius/AutoRecon.git

echo "Setting sudoautorecon Alias"

if [[ $SHELL == *"zsh"* ]]; then
    echo 'alias sudoautorecon="sudo $(which autorecon)"' >> ~/.zshrc
    source ~/.zshrc
elif [[ $SHELL == *"bash"* ]]; then
    echo 'alias sudoautorecon="sudo $(which autorecon)"' >> ~/.bashrc
    source ~/.bashrc
else
    echo "Unknown shell. Please manually set sudo alias."
fi

echo "AutoRecon installation completed!"
```

## Commands



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 8th 2023 (07:44 am) 
Last Modified Date: June 8th 2023 (07:44 am)
