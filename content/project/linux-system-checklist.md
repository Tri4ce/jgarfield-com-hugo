1. Check for latest version of Distribution
2. Download latest Distribution
3. Checksum download
4. 
5. 

disable password logins entirely

http://www.unixwiz.net/techtips/ssh-agent-forwarding.html

# google auth

pacman -S --needed base-devel git qrencode

git clone https://aur.archlinux.org/libpam-google-authenticator.git

cd libpam-google-authenticator
makepkg -si



# systemctl edit sshd.socket
[Socket]
ListenStream=
ListenStream=192.168.1.10:12345
FreeBind=true

/etc/ssh/sshd_config
Port 12345
PasswordAuthentication no


systemctl restart sshd.socket

