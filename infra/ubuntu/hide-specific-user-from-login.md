---
description: Hide a specific user from the login screen on Ubuntu 22.04 Desktop
---

# Hide specific user from login

To hide a user named `XXX`, create a file named

```
/var/lib/AccountsService/users/XXX
```

containing two lines:

```
[User]
SystemAccount=true
```

If the file already exists, make sure you append the `SystemAccount=true` line to the `[User]` section.

The change takes effect after reloading AccountsService:

```
sudo systemctl restart accounts-daemon.service
```



{% embed url="https://askubuntu.com/questions/92349/how-do-i-hide-a-particular-user-from-the-login-screen" %}
