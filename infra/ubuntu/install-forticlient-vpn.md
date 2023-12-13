---
description: How to install Forticlient VPN on Ubuntu Desktop 22.04
---

# Install FortiClient VPN

**To install on Ubuntu 22.04 LTS:**

1.  Install the gpg key:

    `wget -O - https://repo.fortinet.com/repo/forticlient/7.2/debian/DEB-GPG-KEY | gpg --dearmor | sudo tee /usr/share/keyrings/repo.fortinet.com.gpg`
2.  Create `/etc/apt/sources.list.d/repo.fortinet.com.list` with the following content:

    deb \[arch=amd64 signed-by=/usr/share/keyrings/repo.fortinet.com.gpg] https://repo.fortinet.com/repo/forticlient/7.2/debian/ stable non-free
3.  Update package lists:

    `sudo apt-get update`
4.  Install FortiClient:

    `sudo apt install forticlient`



{% embed url="https://docs.fortinet.com/document/forticlient/7.2.2/linux-release-notes/213138/install-forticlient-linux-from-repo-fortinet-com" %}
