# Using WSL to use ansible and vagrant in windows

In Windows:

Powershell Admin:
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
Powershell:

```
> Invoke-WebRequest -Uri https://aka.ms/wslubuntu2004 -OutFile Ubuntu.appx -UseBasicParsing
> Rename-Item .\Ubuntu.appx .\Ubuntu.zip
> Expand-Archive .\Ubuntu.zip .\Ubuntu
> cd .\Ubuntu\
> .\ubuntu2004.exe
```
Open Ubuntu
in Ubuntu:
```
$ export VAGRANT_WSL_ENABLE_WINDOWS_ACCESS="1"
$ export PATH="$PATH:/mnt/c/Program Files/Oracle/VirtualBox"
```

Install Ansible:
```
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```
If needed install unzip
```
$ sudo apt install unzip
```

Install vagrant
```
$ wget https://releases.hashicorp.com/vagrant/2.2.10/vagrant_2.2.10_linux_amd64.zip
$ unzip vagrant_2.2.10_linux_amd64.zip
$ sudo mv vagrant /usr/local/bin/ && rm vagrant_2.2.10_linux_amd64.zip
```



Used Sources:
- https://www.vagrantup.com/docs/other/wsl
- https://docs.microsoft.com/en-us/windows/wsl/install-on-server
- https://docs.microsoft.com/en-us/windows/wsl/install-manual
