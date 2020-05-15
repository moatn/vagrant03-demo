# Vagrant demo

With this vagrant repo, you install one ubuntu 18.04 bionic beaver machine. 

This repo is intended for educational purposes only. 

## Prerequisites

This setup is badly tested (: 

Works on MacOS Catalina.

Software needed:

- Vagrant 2.2.6 or higher
- virtualbox 5.0 or higher
- virtualbox extension pack

__Windows users__

For windows, `git` is needed on the commandline. You can use the Windows packet manager `Chocolatey` for `Powershell` to easily install `git`. 

Chocolatey url
```
https://chocolatey.org/install
```

To install `git` with `Chocolatey` within `Powershell`:
```powershell
choco install git
```

### MacOS Catalina

```bash
brew install vagrant
```

### Ubuntu 18.04

```bash 
apt install -y vagrant
```

### Windows 

Download url
```
https://www.vagrantup.com/downloads.html
```

## Howto start the Vagrant box

```
git clone https://github.com/moatn/vagrant03-demo
cd vagrant03-demo
vagrant up
```

```
vagrant ssh lb01
```

## Overview hostnames/ip-addresses

Vagrant name | Hostname | IP Address
--- | --- | ---
lb01  | lb01.local  | 192.168.50.10
web01 | web01.local | 192.168.50.12
web02 | web02.local | 192.168.99.13
