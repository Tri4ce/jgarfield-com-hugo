+++
date = "2017-05-23T13:27:28+05:00"
draft = false
title = "Arch Linux sshd Configuration"
image = "arch-linux-sshd-configuration.png"
+++

# Install openSSH package

``` zsh
pacman -S openssh
```


# Create Group and Add Users

``` zsh
groupadd ssh-users
usermod -aG ssh-users jimbob
```


# SSH Keys

"SSH keys serve as a means of identifying yourself to an SSH server using public-key cryptography and challenge-response authentication. One immediate advantage this method has over traditional password authentication is that you can be authenticated by the server without ever having to send your password over the network. Anyone eavesdropping on your connection will not be able to intercept and crack your password because it is never actually transmitted. Additionally, using SSH keys for authentication virtually eliminates the risk posed by brute-force password attacks by drastically reducing the chances of the attacker correctly guessing the proper credentials."


# /etc/ssh/sshd_config

Banner /etc/issue
HostKey /etc/ssh/ssh_host_rsa_key
Port 39901


# Configure /etc/issue

### SECURITY ###
While /etc/issue can contain many special escape sequences to display things like the current date/time, the amount of users logged-in, etc., I would HIGHTLY recommend not using any of these sequences if you plan on exposing anything like sshd to the internet. The more real-time details you provide about your system, the larger your attack surface becomes, offering insight immediately to parties interested in compromising your system.

# Configure /etc/issue.net (optional)

# Configure /etc/motd



# Resources

* https://wiki.archlinux.org/index.php/SSH_keys
* https://wiki.archlinux.org/index.php/Secure_Shell
* http://www.linuxfromscratch.org/blfs/view/svn/postlfs/logon.html
* http://man7.org/linux/man-pages/man5/ssh_config.5.html
