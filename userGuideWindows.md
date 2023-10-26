# For windows pro version

## windows server docker installation [Click for GitHub](https://github.com/microsoft/Windows-Containers/blob/Main/helpful_tools/Install-DockerCE/install-docker-ce.ps1) [Click here for blog](https://www.virtualizationhowto.com/2022/09/install-docker-on-windows-server-2022/)
```
Invoke-WebRequest -UseBasicParsing "https://raw.githubusercontent.com/microsoft/Windows-Containers/Main/helpful_tools/Install-DockerCE/install-docker-ce.ps1" -o install-docker-ce.ps1
```
```
.\install-docker-ce.ps1
```
## Document to install docker desktop as Hyper-V backend and Windows containers for more [Click here](https://docs.docker.com/desktop/install/windows-install/)

**Note:** Please run all below command in windows powershell in **administrator**

Step 1: enable the hyper-v and container feature
```
Enable-WindowsOptionalFeature -Online -FeatureName $("Microsoft-Hyper-V", "Containers") -All
```
Step 2: Please check hyper-v and containers are enabled
```
Get-WindowsOptionalFeature -Online
```
Step 3: download the docker desktop [Click here](https://www.docker.com/products/docker-desktop/)
```
Invoke-WebRequest -Uri https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe -OutFile DockerDesktopInstaller.exe
```
Step 4: install docker desktop
```
Start-Process -Wait -FilePath .\DockerDesktopInstaller.exe
```
Step 5: Remove the installer
```
Remove-Item .\DockerDesktopInstaller.exe
```

# For windows Home version and pro version

## Document to install docker desktop as WSL 2 backend for more [Click here](https://docs.docker.com/desktop/install/windows-install/)

**Note:** Please run all below command in windows powershell in **administrator**

Step 1: Open PowerShell as Administrator and run this command to enable the WSL feature
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

Step 2: Enable the 'Virtual Machine Platform' optional feature
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
Step 3: Install WSL for more [Click here](https://learn.microsoft.com/en-us/windows/wsl/install)
```
wsl --install
```
Step 4: If WSL already present please update it
```
wsl --update
```
Step 5: Set WSL 2 as your default version
```
wsl --set-default-version 2
```
Step 6: download the docker desktop [Click here](https://www.docker.com/products/docker-desktop/)
```
Invoke-WebRequest -Uri https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe -OutFile DockerDesktopInstaller.exe
```
Step 7: install docker desktop
```
Start-Process -Wait -FilePath .\DockerDesktopInstaller.exe
```
Step 8: Remove the installer
```
Remove-Item .\DockerDesktopInstaller.exe
```
