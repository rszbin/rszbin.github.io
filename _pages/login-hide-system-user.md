# Hide Users From Login Page

**Modify the user file**
sudo vim /var/lib/AccountsService/users/username

**Set system account to true**
[User]
SystemAccount=true

**Restart the AccountsService**
sudo systemctl restart accounts-daemon.service
