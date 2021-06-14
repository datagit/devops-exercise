# Linux  Distribution

# Shell Commands

# Linux Directory Structure

# file system explain
```java
https://www.guru99.com/file-permissions.html
UserGroupOther
r = read permission
w = write permission
x = execute permission
- = no permission

chmod
chown
ls -l
```
# Linux/Unix SSH, Ping, FTP, Telnet Communication Commands
```java
ssh username@ip-address or hostname
ping 172.16.170.1
ftp ftp.javatutorialhub.com
// has authentication user/pass
ftp linux@ftp.javatutorialhub.com
telnet localhost 80
```

# SSH Key Mgmt
```java
# https://xuanthulab.net/tao-ssh-key-va-xac-thuc-ket-noi-ssh-bang-public-private-key.html
# create -> SSH Key (Public/Private)
ssh(Secure Shell)
  guide: https://www.youtube.com/watch?v=x20NiW2BM3Y
  client
    ssh:22
  server
    openssh:22
      https://www.openssh.com/
tools
  ssh-keygen
    https://www.ssh.com/ssh/keygen/
key pair
  public key(O-KHOA)
  private key(CHIA-KHOA)
    *.pem: a file was encode with base64, and it is private key

ssh-keygen -t rsa
tree ~/.ssh/
/Users/datdao/.ssh/
├── config
├── connectTpoint.pem
├── id_ed25519 -> just created
├── id_ed25519.pub -> just created
└── known_hosts

```
# common commands
```bash
# Detect open port in linux: way 1, in container
lsof -ti :8080 | xargs kill -9
# Detect open port in linux: way 2, check by ip
telnet localhost 8080
# check response header
curl -I https://www.google.com.vn

top -> filter
htop -> filter, search
tree
```

