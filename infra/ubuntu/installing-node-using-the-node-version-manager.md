---
description: How To Install Node.js on Ubuntu 22.04
---

# Installing Node Using the Node Version Manager

The Node version from Ubuntu apt repo looks a bit outdated:

```
fcolomer@arabesco:~$ npm --version
8.5.1
```

Considering that latest version as of&#x20;

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Another way of installing Node.js that is particularly flexible is to use **nvm**, the Node Version Manager. This piece of software allows you to install and maintain many different independent versions of Node.js, and their associated Node packages, at the same time.

{% @github-files/github-code-block %}
