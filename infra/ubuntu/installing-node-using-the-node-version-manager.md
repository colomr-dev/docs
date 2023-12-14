---
description: How To Install Node.js on Ubuntu 22.04
---

# NodeJS install using nvm

Apart of install node via apt, another way of installing Node.js that is particularly flexible is to use **nvm**, the Node Version Manager.&#x20;

{% @github-files/github-code-block %}

This piece of software allows you to install and maintain many different independent versions of Node.js, and their associated Node packages, at the same time.

To install nvm :

```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

This will install the nvm script to your user account. To use it, you must first source your .bashrc file:

```bash
source ~/.bashrc
```

As the v20.x branch is the most stable so far, let's take a look to remote available repos:

```bash
fcolomer@arabesco:~$ nvm list-remote |egrep -i LTS |egrep v20
        v20.9.0   (LTS: Iron)
       v20.10.0   (Latest LTS: Iron)

```

### Installing Node.js (nvm)

`node_version` = v20.10.0 or corresponding version

```bash
nvm install node_version
```

if not specific version is required, it is better to issue:

`nvm install --lts`

To install the **latest LTS version**

### Removing Node.js  (apt, nvm)

You can uninstall Node.js using **apt** or **nvm.**

`apt remove nodejs` or `nvm unistall node_version`
