---
description: How To Install Node.js on Ubuntu 22.04
---

# NodeJS install using nvm

The Node version from Ubuntu apt repo looks a bit outdated:

```
fcolomer@arabesco:~$ npm --version
8.5.1
```

Considering that latest version as of  December 2023 is v21.4

Another way of installing Node.js that is particularly flexible is to use **nvm**, the Node Version Manager.&#x20;

{% @github-files/github-code-block %}

This piece of software allows you to install and maintain many different independent versions of Node.js, and their associated Node packages, at the same time.

To install nvm :

```
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

This will install the nvm script to your user account. To use it, you must first source your .bashrc file:

```
source ~/.bashrc
```

As the v20.x branch is the most stable so far, let's take a look to remote available repos:

```
fcolomer@arabesco:~$ nvm list-remote |egrep -i LTS |egrep v20
        v20.9.0   (LTS: Iron)
       v20.10.0   (Latest LTS: Iron)

```

### Installing Node.js from nvm

`node_version` = v20.10.0 or corresponding version

```
nvm install node_version
```

### Removing Node.js&#x20;

You can uninstall Node.js using **apt** or **nvm.**

`apt remove nodejs` or `nvm unistall node_version`
