# Docker in windows
How to setup Docker in windows 10

Install WSL and config default version 2.
```
wsl --install
wsl --set-default-version 2
```

In Window 10 setting, go to **Windows Features**.
In here, confirm "Hyper-V", "Virtual Machine Platform" and "Windows Subsystem for Linux". These should be enabled.
If disabled, check and click "Ok"
![image](https://github.com/sip-materials/docker-with-windows/assets/162189968/f59d28ad-d91a-4002-8be8-278f89ca6d7b)

Go to Start menu open run by press Ctrl + R and open gpedit.msc.
Go to Local Computer Policy/Computer Configuration/Administrative Templates/System/Device Guard and open Turn On Virtualization Based Security.
And disable Turn On Virtualization Based Security.
![image](https://github.com/sip-materials/docker-with-windows/assets/162189968/0ae4bbb4-0b72-430a-839d-84245be702b9)

Reboot the system.

Try to run Docker Desktop.
If face error message of "Unexpected WSL error", try to run 2 commands.
```
# Open powershell as Administrator
bcdedit /set hypervisorlaunchtype off
# After excuting the command,
bcdedit /set hypervisorlaunchtype auto
```
![image](https://github.com/sip-materials/docker-with-windows/assets/162189968/beb584fb-4300-431f-88ad-a1b519327dce)

If vmware is not working, try to run command
```
bcdedit /set hypervisorlaunchtype off
```
Then reboot OS and try again.
